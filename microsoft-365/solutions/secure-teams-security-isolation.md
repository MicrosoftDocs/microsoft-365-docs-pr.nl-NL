---
title: Een team configureren met beveiligingsisolatie
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Informatie over het maken van een team met een uniek gevoeligheidslabel voor beveiliging.
ms.openlocfilehash: 2ecd8e0458f6ebef9ebd1b0c3724195cc70f6378
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920926"
---
# <a name="configure-a-team-with-security-isolation"></a>Een team configureren met beveiligingsisolatie

Dit artikel bevat aanbevelingen en stappen om een privéteam in Microsoft Teams te configureren met een uniek gevoeligheidslabel om bestanden te versleutelen, zodat alleen teamleden ze kunnen ontsleutelen.

Naast de privétoegang beschrijft dit artikel hoe u de bijbehorende SharePoint-site kunt configureren, die u kunt openen vanuit de sectie **Bestanden** van een teamkanaal, voor de extra beveiliging die nodig is om sterk gereguleerde gegevens op te slaan.

De elementen van de configuratie van een team met beveiligingsisolatie zijn:

- Een privéteam
- Extra beveiliging voor de onderliggende SharePoint-site voor het team waarmee:
  - Wordt voorkomen dat leden van de site de site delen met anderen.
  - Wordt voorkomen dat niet-leden van de site toegang tot de site vragen.
- Een gevoeligheidslabel specifiek voor dit team dat:
    - Voorkomt toegang tot SharePoint-inhoud vanaf niet-beheerde apparaten
    - Maakt gasttoegang tot het team mogelijk of weigert deze, afhankelijk van uw vereisten
    - Versleutelt documenten waarop het label wordt toegepast

> [!IMPORTANT]
> Zorg ervoor dat u [gevoeligheidslabels hebt ingeschakeld om de inhoud van Microsoft teams, Office 365-groepen en SharePoint-sites te beveiligen](../compliance/sensitivity-labels-teams-groups-sites.md), voordat u verder gaat met de stappen in dit artikel.

Bekijk deze video voor een overzicht van het implementatieproces.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> Zie de [poster Microsoft Teams met beveiligingsisolatie](../downloads/team-security-isolation-poster.pdf) voor een samenvatting van één pagina van dit scenario.

[![Poster Microsoft Teams met beveiligingsisolatie](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)

U kunt deze poster ook downloaden in [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) of [PowerPoint-](https://download.microsoft.com/download/8/0/5/8057fc16-c044-40b6-a652-7ed555ba2895/team-security-isolation-poster.pptx) indeling en afdrukken op papier met formaat Letter, Legal of Tabloid (27,9 x 43,2 cm).

Probeer deze configuratie in uw eigen testlabomgeving met [deze instructies](team-security-isolation-dev-test.md).

Lees in [deze casestudy](contoso-team-for-top-secret-project.md) hoe Contoso Corporation een geïsoleerd team heeft gebruikt voor een uiterst geheim project.

## <a name="initial-protections"></a>Initiële bescherming

Lees de volgende aanbevolen procedures om de toegang tot het team en de onderliggende SharePoint-site te beveiligen:
- [Beleid voor identiteiten en apparaattoegang](../security/office-365-security/identity-access-policies.md)
- [Beleid voor toegang tot SharePoint Online](../security/office-365-security/sharepoint-file-access-policies.md)
- [Teams implementeren met basisbescherming](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a>Delen met gasten

Afhankelijk van de aard van uw bedrijf, is het mogelijk dat u delen met gasten niet wilt inschakelen voor dit team. Als u van plan bent om met personen buiten uw organisatie samen te werken in het team, kunt u delen met gasten inschakelen. 

Voor meer informatie over delen met gasten kunt u de volgende bronnen raadplegen:

- [Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen buiten uw organisatie](./share-limit-accidental-exposure.md)
- [Een beveiligde omgeving voor het delen met gasten maken](./create-secure-guest-sharing-environment.md)

Om delen met gasten toe te staan of te blokkeren, gebruiken we een combinatie van een gevoeligheidslabel voor het team en besturingselementen voor delen op siteniveau voor de bijbehorende SharePoint-site, die beide later worden besproken.

## <a name="create-a-private-team"></a>Een privéteam maken

Aangezien we specifiek een gevoeligheidslabel voor dit team maken, is de volgende stap het maken van het team zelf. Als u al een bestaand team hebt, kunt u dat gebruiken.

Een team maken voor vertrouwelijke informatie
1. Klik links in Teams op **Teams** en klik onderaan de lijst met teams op **Deelnemen aan een team of een team maken**.
2. Klik op **Team maken** (eerste kaart, linkerbovenhoek).
3. Kies **Een volledig nieuw team maken**.
4. Behoudt in de lijst **gevoeligheid** de standaardwaarde.
5. Klik onder **privacy** op **persoonlijk**.
6. Typ een naam voor het team dat is gerelateerd aan uw vertrouwelijke project. Bijvoorbeeld **Project Saturnus**.
7. Klik op **Maken**.
8. Voeg gebruikers toe aan het team en klik vervolgens op **sluiten**.

## <a name="private-channel-settings"></a>Instellingen voor privékanaal

U wordt aangeraden het maken van persoonlijke kanalen tot teameigenaren te beperken.

Het maken van een persoonlijk kanaal beperken
1. In het team klikt u op **Meer opties** en klikt u vervolgens op **Team beheren**.
2. Vouw op het tabblad **Instellingen** de optie **Machtigingen voor leden** uit.
3. Schakel het selectievakje **Leden toestaan privékanalen te maken** uit.

U kunt ook [teambeleid](/MicrosoftTeams/teams-policies) gebruiken om te bepalen wie persoonlijke kanalen kan maken.

## <a name="create-a-sensitivity-label"></a>Een gevoeligheidslabel maken

Voor het configureren van een team voor beveiligingsisolatie wordt een gevoeligheidslabel gebruikt dat specifiek is gemaakt voor dit team. Dit label wordt op teamniveau gebruikt om het delen van gasten te controleren en de toegang vanaf onbeheerde apparaten te blokkeren. Het kan ook worden gebruikt om individuele bestanden in het team te classificeren en te versleutelen, zodat alleen teameigenaren en leden ze kunnen openen.

Als u een interne partner- of stakeholdergroep heeft die versleutelde documenten wel moet kunnen bekijken, maar niet bewerken, kunt u hen met machtigingen voor alleen-lezen aan het label toevoegen. Vervolgens kun je deze personen met lezer-machtigingen aan de SharePoint-site van het team toevoegen en hebben ze alleen-lezen toegang tot de site waar de documenten worden bewaard, maar niet tot het team zelf.


Een gevoeligheidslabel maken
1. Open het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com).
2. Klik onder **Oplossingen** op **Informatiebeveiliging**.
3. Klik op **Een label maken**.
4. Geef een naam op voor het label. We suggereren het te vernoemen naar het team waarmee je het zal gebruiken.
5. Voeg een weergavenaam en een beschrijving toe en klik vervolgens op **Volgende**.
6. Selecteer op de **pagina Het bereik voor dit label definiëren** de opties **Bestanden en e-mailberichten** en **Groepen en sites** en klik op **Volgende**.
7. Selecteer op de pagina **Beveiligingsinstellingen voor bestanden en e-mailberichten kiezen** de optie **Bestanden en e-mailberichten versleutelen** en klik vervolgens op **Volgende**.
8. Kies op de pagina **Versleuteling** de optie **Versleutelingsinstellingen configureren**.
9. Klik op **Gebruikers of groepen toevoegen**, selecteer het team dat je hebt gemaakt en klik vervolgens op **Toevoegen.**
10. Klik op **Machtigingen kiezen**.
11. Kies **co-auteurs** in de vervolgkeuzelijst en klik vervolgens op **opslaan**.
12. Als u gebruikers of groepen wilt opnemen met alleen-lezen toegang tot bestanden met het label:
    1. Klik op **Machtigingen toewijzen**.
    1. Klik op **Gebruikers of groepen toevoegen**, selecteer de gebruikers of groepen die je hebt gemaakt en klik vervolgens op **Toevoegen**.
    1. Klik op **Machtigingen kiezen**.
    1. Kies **Viewer** in de vervolgkeuzelijst en klik vervolgens op **Opslaan**.
13.  Klik op **Opslaan** en klik vervolgens op **Volgende**.
14. Klik op de pagina *Automatische labeling voor bestanden en e-mailberichten* op **Volgende**.
15. Selecteer op de pagina **Beveiligingsinstellingen voor groepen en sites definiëren** de opties **Instellingen voor privacy en toegang voor externe gebruikers** en **Instellingen voor toegang tot apparaten en instellingen voor extern delen** en klik op **Volgende**.
16. Selecteer op de pagina **Instellingen voor privacy en toegang voor externe gebruikers definiëren** onder **Privacy** de optie **Privé**.
17. Als je gasttoegang wilt toestaan, selecteer je onder **Toegang voor externe gebruikers** de optie **Laat Microsoft 365-groepseigenaren personen van buiten de organisatie als gast aan de groep toevoegen**.
18. Klik op **Volgende**.
19. Selecteer op de pagina **Instellingen voor extern delen en instellingen voor toegang tot het apparaat definiëren** de optie **Extern delen beheren via gelabelde SharePoint-sites**.
20. Onder **Inhoud kan worden gedeeld met** kies je **Nieuwe en bestaande gasten** als je gasttoegang wilt toestaan of **Alleen personen binnen uw organisatie** als je dat niet wilt.
21. Kies onder **Toegang tot niet-beheerde apparaten** de optie **Toegang blokkeren**.
22. Klik op **Volgende**.
23. Klik op de pagina **Automatische labeling voor databasekolommen** op **Volgende**.
24. Klik op **Label maken** en klik vervolgens op **Gereed**.

Nadat u het label heeft gemaakt, moet u het publiceren voor de gebruikers die het zullen gebruiken. In dit geval maken we het label alleen beschikbaar voor personen in het team.

Een gevoeligheidslabel publiceren
1. Kies in het Microsoft 365-compliancecentrum op de pagina **Informatiebeveiliging** het tabblad **Labelbeleid**.
2. Klik op **Labels publiceren**.
3. Klik op de pagina **Kies gevoeligheidslabels om te publiceren** op **Kies gevoeligheidslabels om te publiceren**.
4. Selecteer het label dat u hebt gemaakt en klik vervolgens op **toevoegen**.
5. Klik op **Volgende**.
6. Klik op de pagina Publiceren voor gebruikers en groepen op **Gebruikers en groepen kiezen**.
7. Klik op **toevoegen** en selecteer vervolgens het team dat u hebt gemaakt.
8. Klik op **Toevoegen** en klik op **Gereed**.
9. Klik op **Volgende**.
10. Schakel op de pagina beleidsinstellingen het selectievakje **gebruikers moeten redenen geven om een label of lagere classificatielabel te verwijderen** in en klik vervolgens op **volgende**.
11. Typ een naam voor het beleid en klik vervolgens op **volgende**.
12. Klik op **Verzenden** en klik vervolgens op **Gereed**.

## <a name="apply-the-label-to-the-team"></a>Het label toepassen op het team

Zodra het label is gepubliceerd, moet u het op het team toepassen om de instellingen voor het delen van gasten en beheerde apparaten van kracht te laten worden. Dit doet u in het SharePoint-beheercentrum. Het kan even duren voordat het label beschikbaar is nadat het is gepubliceerd.

Het gevoeligheidslabel toepassen
1. Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).
2. Klik onder **Sites** op **Actieve sites**.
3. Klik op de site die is gekoppeld aan het team.
4. Klik op het tabblad **beleid** onder **gevoeligheid** op **bewerken**.
5. Selecteer het label dat u hebt gemaakt en klik vervolgens op **opslaan**.

## <a name="sharepoint-settings"></a>SharePoint-instellingen

Er zijn drie stappen die moeten worden uitgevoerd in SharePoint:

- Werk de instellingen voor het delen met gasten voor de site in het SharePoint-beheercentrum bij zodat deze overeenkomen met wat u hebt gekozen toen u het label maakte, en werk de standaardkoppeling voor delen bij naar *personen met bestaande toegang*.
- Werk de instellingen voor het delen van sites op de site zelf bij om te voorkomen dat leden bestanden, mappen of de site delen, en schakel toegangsaanvragen uit.
- Als u mensen of groepen aan het label hebt toegevoegd met Viewer-rechten, kunt u ze met lezersrechten toevoegen aan de SharePoint-site.

### <a name="sharepoint-guest-settings"></a>SharePoint-gastinstellingen

De instelling voor het delen met gasten die u hebt gekozen toen u het label maakte (die alleen van invloed is op het teamlidmaatschap), moet als volgt overeenkomen met de instellingen voor het delen met gasten voor de bijbehorende SharePoint-site:

|Labelinstelling|Instelling voor een SharePoint-site|
|:------------|:----------------------|
|**Laat Office 365-groepseigenaren mensen buiten de organisatie toevoegen aan de groep** geselecteerd|**Nieuwe en bestaande gasten** (standaard voor nieuwe teams)|
|**Laat Office 365-groepseigenaren mensen buiten de organisatie toevoegen aan de groep** niet geselecteerd|**Alleen personen binnen uw organisatie**|

We zullen ook het standaard koppelingstype voor delen bijwerken om het risico te verkleinen dat bestanden en mappen per ongeluk worden gedeeld met een breder publiek dan bedoeld.

Site-instellingen bijwerken
1. Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).
2. Klik onder **Sites** op **Actieve sites**.
3. Klik op de site die is gekoppeld aan het team.
4. Klik op het tabblad **Beleid** onder **Extern delen** op **Bewerken**.
5. Als u de functie delen met gasten hebt toegestaan tijdens het maken van het gevoelige label, moet u ervoor zorgen dat **nieuwe en bestaande gasten** is geselecteerd. Als u delen niet hebt toegestaan toen u het label maakte, kiest u **Alleen mensen in uw organisatie**.
6. Schakel onder Standaard koppelingstype voor delen het selectievakje **Hetzelfde als instelling op organisatieniveau** uit en selecteer **Personen met bestaande toegang**.
7. Klik op **Opslaan**.

#### <a name="private-channels"></a>Privékanalen

Als u privékanalen aan het team toevoegt, maakt elk privékanaal een nieuwe SharePoint-site met de standaardinstellingen voor delen. Deze sites zijn niet zichtbaar in het SharePoint-beheercentrum, dus u moet de [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) PowerShell-cmdlet gebruiken met de volgende parameters om de instellingen voor het delen van gasten bij te werken:

- `-SharingCapability Disabled` om delen met gasten uit te schakelen (deze is standaard ingeschakeld)
- `-DefaultSharingLinkType Internal` om de standaard koppeling voor delen te wijzigen in *specifieke personen*

Als u niet van plan bent om privékanalen met uw team te gebruiken, overweeg dan om de mogelijkheid voor teamleden uit te schakelen om ze te maken onder **ledenmachtigingen** in [teaminstellingen](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc).

### <a name="site-sharing-settings"></a>Standaardinstellingen voor het delen van een site

Om ervoor te zorgen dat de SharePoint-site niet wordt gedeeld met personen die geen deel uitmaken van het team, beperken we het delen ervan tot eigenaren. We beperken ook het delen van bestanden en mappen tot de teameigenaren. Dit helpt ervoor te zorgen dat eigenaren weten wanneer een bestand wordt gedeeld met iemand buiten het team.

Om het delen van sites met eigenaren te configureren
1. Ga in Teams naar het tabblad **Algemeen** van het team dat u wilt bijwerken.
2. Klik op de werkbalk van het team op **Bestanden**.
3. Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.
4. Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.
5. Klik in het deelvenster Site-machtigingen, onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.
6. Kies onder **Machtigingen voor delen** de optie **Alleen site-eigenaren kunnen bestanden, mappen en de site delen** en klik vervolgens op **Opslaan**.

### <a name="custom-site-permissions"></a>Aangepaste site-machtigingen

Als u personen met een weergavemachtiging hebt toegevoegd aan het gevoeligheidslabel, kunt u hen toevoegen aan de SharePoint-site met leestoegang, zodat ze gemakkelijk toegang hebben tot de bestanden.

Gebruikers toevoegen aan de site
1. Klik op de site op het pictogram instellingen en klik vervolgens op **site-machtigingen**.
2. Klik op **personen uitnodigen** en klik vervolgens op **alleen site delen**.
3. Typ de namen van de gebruikers en groepen die u wilt uitnodigen.
4. Voor elke persoon of groep die u toevoegt, wijzigt u de machtigingen van **bewerken** naar **lezen**.
5. Kies of u hen een e-mailbericht met een koppeling naar de site wilt sturen.
6. Klik op **Toevoegen**.

## <a name="additional-protections"></a>Aanvullende beveiligingsmaatregelen

Microsoft 365 biedt aanvullende methoden voor het beveiligen van uw inhoud. Overweeg of de volgende opties de beveiliging van uw organisatie zouden kunnen verbeteren.

- Laat je gastgebruikers akkoord gaan met de [gebruiksrechtovereenkomst](/azure/active-directory/conditional-access/terms-of-use).
- Configureer een [beleid voor de time-out van een sessie](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) voor gasten.
- Maak [gevoelige informatietypen](../compliance/sensitive-information-type-learn-about.md) en gebruik [gegevensverliesbeveiliging](../compliance/data-loss-prevention-policies.md) om beleid in te stellen rond toegang tot gevoelige informatie.
- Gebruik [Azure Active Directory-toegangsbeoordelingen](/azure/active-directory/governance/access-reviews-overview) om periodiek teamtoegang en lidmaatschap te controleren.

## <a name="drive-user-adoption-for-team-members"></a>Ingebruikname door teamleden bevorderen

Nu het team is ingesteld, is het tijd om de ingebruikname van dit team en de extra beveiliging te bevorderen bij de teamleden.

### <a name="train-your-users"></a>Uw gebruikers trainen

Leden van de teamgroep hebben toegang tot het team en alle bijbehorende resources, inclusief chats, vergaderingen en andere apps. Wanneer u werkt met bestanden in de sectie **Bestanden** van een kanaal, moeten leden van het team het gevoeligheidslabel toewijzen aan de bestanden die ze zelf hebben gemaakt.

Wanneer het label wordt toegepast op het bestand, is het beveiligd. Leden van het team kunnen het openen en in realtime samenwerken. Als het bestand de site verlaat en wordt doorgestuurd naar een kwaadwillende gebruiker, moeten ze de inloggegevens opgeven van een gebruikersaccount dat lid is van het team om het bestand te openen en de inhoud ervan te bekijken. 

Leer uw teamleden:

- Over het belang van het gebruik van het nieuwe team voor chats, vergaderingen, bestanden en de andere bronnen van de SharePoint-site en de gevolgen van een sterk gereguleerd datalek, zoals juridische gevolgen, boetes, ransomware of verlies van concurrentievoordeel.
- hoe ze toegang hebben tot het team.
- hoe ze nieuwe bestanden op de site kunnen maken en nieuwe bestanden kunnen uploaden die lokaal zijn opgeslagen.
- Informatie over het labelen van bestanden met het juiste gevoeligheidslabel voor het team.
- De manier waarop bestanden door het label worden beschermd, zelfs als deze worden gelekt.

Bij deze training horen praktijkoefeningen, zodat de teamleden deze functies en de resultaten ervan kunnen ervaren.

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a>Periodiek het gebruik bekijken en feedback van teamleden verwerken

In de weken na de training:

- Verwerk de feedback van teamleden snel en verfijn beleidsregels en configuraties.
- Analyseer het gebruik van het team en vergelijk dit met gebruiksverwachtingen.
- Verifieer dat gereglementeerde bestanden juist zijn gelabeld met het gevoeligheidslabel. (U kunt zien welke bestanden een label hebben door een map te bekijken in SharePoint en de kolom **Gevoeligheid** toe te voegen met de optie **Kolommen weergeven/verbergen** of **Kolom toevoegen**.

School de gebruikers indien nodig bij.

## <a name="see-also"></a>Zie ook

[Azure AD Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-configure)