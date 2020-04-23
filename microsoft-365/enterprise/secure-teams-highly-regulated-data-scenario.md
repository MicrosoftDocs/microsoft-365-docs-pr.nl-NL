---
title: Teams voor sterk gereglementeerde gegevens
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Maak een beveiligd team om de meest waardevolle en gevoeligste bestanden op te slaan.
ms.openlocfilehash: 95c0fc4177f2a16fc79dd0833809f4405e8cdda9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631391"
---
# <a name="teams-for-highly-regulated-data"></a>Teams voor sterk gereglementeerde gegevens

Dit artikel bevat aanbevelingen en stappen voor het configureren van een privéteam in Microsoft Teams waarmee alleen toegang wordt verleend tot Teams-functies, zoals chats, vergaderingen en bestanden, aan leden en eigenaren van de Microsoft 365-groep voor het team. 

Naast de privétoegang op basis van de Microsoft 365-groep, wordt in dit artikel beschreven hoe u de onderliggende SharePoint-privéteamsite configureert die u kunt openen vanuit de sectie **Bestanden** van een teamkanaal, voor de extra beveiliging die nodig is voor het opslaan van sterk gereglementeerde gegevens. Op deze SharePoint-teamsite kunt u bestanden, pagina's, een gedeelde agenda, taken, een notitieblok en lijsten opslaan en hieraan samenwerken.

>[!Note]
> Een vergelijkbaar scenario waarin SharePoint wordt gebruikt, vindt u [hier](teams-sharepoint-online-sites-highly-regulated-data.md).
>

De elementen van de configuratie van een team voor sterk gereglementeerde gegevens zijn:

- Een privéteam met een bijbehorende Microsoft 365-groep met gebruikersaccounts voor eigenaren en leden.
- Extra beveiliging voor de onderliggende SharePoint-site voor het team waarmee:
  - Wordt voorkomen dat leden van de site toegang verlenen aan anderen.
  - Wordt voorkomen dat niet-leden van de site toegang tot de site vragen.
- Een retentielabel voor de onderliggende SharePoint-site dat automatisch wordt toegepast op nieuwe bestanden op de site als standaardmethode voor het definiëren van bewaarbeleid.
- Een beleid voor preventie van gegevensverlies (DLP) waarbij het retentielabel wordt gebruikt en gebruikers de bestanden niet kunnen delen of buiten de organisatie kunnen verzenden.
- Een gevoeligheidslabel of een sublabel van een sterk gereglementeerd label waarvoor versleuteling is ingeschakeld en machtigingen voor Medeauteurs zijn ingesteld voor de Microsoft 365-groep van het team. Gebruikers passen het label of sublabel toe op bestanden die zijn opgeslagen in de sectie **Bestanden** van het team met de optie **Gevoeligheid** op de menubalk in Word, Excel en PowerPoint.

Hier ziet u de resulterende configuratie met een gevoeligheidslabel.

![De configuratie van het scenario voor het beveiligde team](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

Bekijk deze korte video voor een kort overzicht.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a>Zie de [Poster voor Teams voor sterk gereglementeerde gegevens](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) voor een overzicht van één pagina van dit scenario.

[![Poster voor teams voor sterk gereglementeerde gegevens](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)

U kunt deze poster ook downloaden in [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) of [PowerPoint-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx) indeling en deze afdrukken op papier met formaat Letter, Legal of Tabloid (27,9 x 43,2 cm).

## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a>Fase 1: Een team configureren voor sterk gereglementeerde gegevens

De configuratie van de end-to-end-servers bestaat uit de volgende stappen:

1. Identiteit en apparaattoegang configureren.
2. Een privéteam maken.
3. De onderliggende SharePoint-site configureren voor extra beveiliging.
4. Een retentielabel en DLP-beleid maken.
5. Het label of sublabel van het sterk gereglementeerde label maken.

### <a name="step-1-configure-identity-and-device-access"></a>Stap 1: identiteit en apparaattoegang configureren

Als u de toegang tot het team en de SharePoint-site wilt beveiligen, zorgt u ervoor dat u [identiteits- en apparaattoegangsbeleid](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) en het aanbevolen [SharePoint Online-toegangsbeleid](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies) hebt geconfigureerd.

### <a name="step-2-create-a-private-team"></a>Stap 2: een privéteam maken

Volg [deze instructies](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) om een privéteam te maken.

Wanneer u een privéteam maakt, zijn dit de standaardmachtigingen:

- De Microsoft 365-groep voor het team (de teamgroep) heeft groepseigenaren en groepsleden
- Voor de onderliggende SharePoint-site voor het team (de teamsite):
  - De beheerders van de siteverzameling zijn geconfigureerd als de eigenaren van de teamgroep
  - Voor de teamsite: 
    - De SharePoint-groep met teamsite-eigenaren, met het machtigingsniveau Volledig beheer, is ingesteld op de eigenaren van de teamgroep
    - De SharePoint-groep met teamsiteleden, met het machtigingsniveau Bewerken, is ingesteld op de leden van de teamgroep
    - De SharePoint-groep met bezoekers van de teamsite, met het machtigingsniveau Lezen, heeft geen groepen of gebruikersaccounts.

Dit zijn de standaardmachtigingen voor de teamsite.

![De standaardmachtigingen van een teamsite](../media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
>Als u de \<teamnaam > SharePoint-groep Eigenaren bekijkt voor het machtigingsniveau Bewerken, wordt \<teamnaam > Eigenaren niet weergegeven.
>

Met de resulterende machtigingen kunnen:

- Eigenaren van de teamgroep de site beheren en beschikken over volledige controle over de inhoud van de site.
- Leden van de teamgroep bestanden op de site maken en bewerken. 

Het onderhoud van machtigingen is hetzelfde als het onderhoud van teamleden en eigenaren.

Dit is de resulterende configuratie tot nu toe.

![Stap 2 van de configuratie van het scenario voor het beveiligde team](../media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a>Stap 3: de onderliggende SharePoint-site configureren voor extra beveiliging

Configureer deze machtigingsinstellingen vanaf de teamsite.

1. Klik in de werkbalk op het pictogram Instellingen en vervolgens op **Site-machtigingen**.
2. Klik in het deelvenster **Site-machtigingen**, onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.
3. Kies onder **Machtigingen voor delen**, **Alleen site-eigenaren kunnen bestanden, mappen en de site delen**.
4. Schakel **Toegangsaanvragen toestaan** uit en klik op **Opslaan**.

Met deze instellingen kunnen leden van de teamsite de teamsite niet delen met andere leden en kunnen niet-leden geen toegang tot de site aanvragen.

Dit is de resulterende configuratie tot nu toe.

![Stap 3 van de configuratie van het scenario voor het beveiligde team](../media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a>Stap 4: een retentielabel en DLP-beleid maken

Volg [deze instructies](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp) om:

1. Een retentielabel voor sterk gereglementeerde gegevens (indien nodig) te maken en te publiceren.
2. De teamsite te configureren voor het in stap 1 gemaakte retentielabel.
3. DLP-beleid te maken voor sterk gereglementeerde gegevens die het in stap 2 gemaakte retentielabel gebruiken en waarmee gebruikers bestanden niet buiten de organisatie kunnen verzenden. U kunt het beleid ook configureren voor aanvullende vereisten, zoals die voor de regelgeving voor gezondheidsinstanties en de financiële sector, op basis van [DLP-beleidssjablonen](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).

Dit is de resulterende configuratie tot nu toe.

![Stap 4 van de configuratie van het scenario voor het beveiligde team](../media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-a-sensitivity-label-or-a-sublabel-of-the-highly-regulated-sensitivity-label"></a>Stap 5: een gevoeligheidslabel of een sublabel maken van het sterk gereglementeerde gevoeligheidslabel

Een beveiligd team heeft, in tegenstelling tot een gevoeligheidslabel voor sterk gereglementeerde gegevens die iedereen op een bestand kan toepassen, een eigen label of sublabel nodig, zodat toegewezen bestanden:

- Versleuteld zijn en dat de versleuteling wordt meeverplaatst met het bestand.
- Aangepaste machtigingen bevatten, zodat alleen leden van de teamgroep ze kunnen openen.

Om dit extra beveiligingsniveau te halen voor bestanden die zijn opgeslagen op de teamsite, moet u een nieuw gevoeligheidslabel configureren dat een afzonderlijk label is of een sublabel van het algemene label voor sterk gereglementeerde bestanden. Alleen leden van de teamgroep zien dit in hun lijst met labels.

Gebruik een gevoeligheidslabel wanneer u een klein aantal labels nodig hebt voor zowel algemeen gebruik als afzonderlijke privéteams. Gebruik een gevoeligheidssublabel wanneer u een groot aantal labels nodig hebt of als u labels wilt organiseren voor privéteams onder het sterk gereglementeerde label.

[Gebruik deze instructies](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) om een afzonderlijk label of sublabel met de volgende instellingen te configureren:

- De naam van het label bevat de naam van het team
- Versleuteling is ingeschakeld.
- De sitegroep heeft machtigingen voor Medeauteurs

Hier ziet u de resulterende configuratie met het nieuwe label.

![Stap 5 van de configuratie van het scenario voor het beveiligde team](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

Hier ziet u de relatie tussen het gevoeligheidslabel en de teamgroep.

![Relatie tussen de teamgroep en de labelmachtigingen](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
>Als u het gevoeligheidslabel of -sublabel configureert voor door de gebruiker gedefinieerde machtigingen of met een vervaldatum, kunt u het bestand niet openen vanuit Teams of SharePoint. U moet een Office-app gebruiken.
>

### <a name="custom-permissions"></a>Aangepaste machtigingen

U kunt ook aangepaste SharePoint-sitemachtigingen configureren voor de teamsite en zo nodig ook het bijbehorende gevoeligheidslabel. Hier volgen twee voorbeelden.

#### <a name="example-1-delegating-sharepoint-site-administration"></a>Voorbeeld 1: het beheer van SharePoint-sites delegeren

Als de teameigenaar geen ervaring heeft met het beheer van SharePoint of het beheer van de teamsite wil delegeren, kan hij of zij het gebruikersaccount van een SharePoint-beheerder toevoegen aan de lijst met teameigenaren. De SharePoint-beheerder heeft dan echter volledige toegang tot het team en alle bijbehorende resources en kan bestanden openen waarop het gevoeligheidslabel is toegepast. 

Om te voorkomen dat er te veel bevoegdheden worden verleend, voegt u het gebruikersaccount van de SharePoint-beheerder toe aan de SharePoint-groep met teamsite-eigenaren in de geavanceerde machtigingsinstellingen van de site. De SharePoint-beheerder kan de site beheren, maar heeft geen toegang tot het team of de bijbehorende resources en kan de bestanden waaraan het gevoeligheidslabel is toegewezen, niet openen.

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a>Voorbeeld 2: alleen-lezen toegang tot bestanden met een label toestaan

Als sommige medewerkers alleen de inhoud van gelabelde bestanden op de teamsite hoeven te bekijken, voegt u hun individuele gebruikersaccounts toe aan de:

- \<teamnaam > groep SharePoint-bezoekers, die standaard het machtigingsniveau Lezen heeft. 
- Het gevoeligheidslabel met de machtigingen voor bezoekers.

Dit zijn de resulterende machtigingen voor het label.

![Voorbeeld van aangepaste machtigingen voor het weergeven van gelabelde bestanden](../media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
De sitebezoekers hebben rechtstreeks toegang tot de teamsite en kunnen de inhoud bekijken van bestanden waarop het sublabel is toegepast. Maar omdat ze geen lid zijn van de teamgroep, hebben ze geen toegang tot het team of de bijbehorende resources.


## <a name="phase-2-drive-user-adoption-for-team-members"></a>Fase 2: Ingebruikname door teamleden bevorderen

Nu het team is ingesteld, is het tijd om de ingebruikname van dit team en de extra beveiliging voor teamleden te stimuleren.

### <a name="step-1-train-your-users"></a>Stap 1: uw gebruikers trainen

Leden van de teamgroep hebben toegang tot het team en alle bijbehorende resources, inclusief chats, vergaderingen en andere apps. Wanneer u werkt met bestanden in de sectie **Bestanden** van een kanaal, moeten leden van de teamgroep het gevoeligheidslabel of -sublabel toewijzen aan bestanden die zijn gemaakt voor het beveiligde team. Hier ziet u een voorbeeld.

![Voorbeeld van een label dat is toegepast op een bestand in een beveiligd team](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
Wanneer het label wordt toegepast op het bestand, is het beveiligd. Leden van de teamgroep kunnen het bestand openen in Teams en in realtime samenwerken. Het bestand is versleuteld en de machtigingen voor medeauteurs zijn ingesteld op de leden van de teamgroep. Als het bestand de site verlaat en wordt doorgestuurd naar een kwaadwillende gebruiker, moet hij of zij referenties opgeven voor een gebruikersaccount dat lid is van de teamgroep om het bestand te openen en de inhoud te bekijken. 

Leer uw teamleden:

- het belang van het gebruik van het nieuwe team voor chats, vergaderingen, bestanden en de andere resources van de teamsite en de consequenties van een gegevenslek van sterk gereglementeerde gegevens, zoals juridische gevolgen, boetes, ransomware of verlies van concurrentievoordeel.
- hoe ze toegang hebben tot het team.
- hoe ze nieuwe bestanden op de site kunnen maken en nieuwe bestanden kunnen uploaden die lokaal zijn opgeslagen.
- hoe het DLP-beleid voorkomt dat ze bestanden extern delen.
- hoe ze het aangepaste label of sublabel voor het team kunnen toepassen op bestanden.
- hoe het label of sublabel bestanden beschermt, zelfs wanneer deze buiten de site worden gelekt.

Bij deze training horen praktijkoefeningen, zodat de teamleden deze functies en de resultaten ervan kunnen ervaren.

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a>Stap 2: periodiek het gebruik bekijken en feedback van teamleden verwerken

In de weken na de training:

- Verwerk de feedback van teamleden snel en verfijn beleidsregels en configuraties.
- Analyseer het gebruik van het team en vergelijk dit met gebruiksverwachtingen.
- Verifieer dat gereglementeerde bestanden juist zijn gelabeld met het aangepaste gevoeligheidslabel of sublabel.

  U kunt zien welke bestanden een label hebben door een map te bekijken in SharePoint en de kolom **Gevoeligheid** toe te voegen met de optie **Kolommen weergeven/verbergen** of **Kolom toevoegen**.

School de gebruikers indien nodig bij.

## <a name="demonstrate-this-in-a-test-environment"></a>Laat dit zien in een testomgeving

Zie [deze instructies](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment) als u uw eigen testomgeving wilt maken om teams te testen op gevoelige en zeer vertrouwelijke bestanden. 

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)

## <a name="how-the-contoso-corporation-used-a-secure-team-for-a-top-secret-project"></a>Hoe Contoso Corporation een beveiligd team gebruikte voor een zeer geheim project

De Contoso Corporation is een fictief maar representatief wereldwijd productieconglomeraat. Bekijk hoe Contoso de ingebruikname van een [beveiligd team](contoso-team-for-top-secret-project.md) heeft gestimuleerd voor een zeer geheim project waarin nieuwe producten en services werden ontwikkeld en op de markt gebracht. 

## <a name="see-also"></a>Zie ook

[SharePoint-sites voor sterk gereglementeerde gegevens](teams-sharepoint-online-sites-highly-regulated-data.md)

[Microsoft 365 Enterprise-bedrijfsworkloads en -scenario's](deploy-workloads.md)

[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)

[Implementatiehandleiding](deploy-microsoft-365-enterprise.md)
