---
title: Teams met bescherming voor zeer vertrouwelijke gegevens configureren
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Informatie over het implementeren van teams met bescherming voor zeer vertrouwelijke gegevens.
ms.openlocfilehash: 7e746ebc81d1ccd9aea2953fd42004715f8d7819
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509264"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a>Teams met bescherming voor zeer vertrouwelijke gegevens configureren

In dit artikel kijken we naar het opzetten van een team met een zeer gevoelig beschermingsniveau. Zorg ervoor dat je de stappen hebt voltooid in [Teams implementeren met basisbeveiliging](configure-teams-baseline-protection.md) voordat je de stappen in dit artikel uitvoert.

Voor deze beveiligingslaag kunt je een vertrouwelijkheidslabel maken dat door uw hele organisatie kan worden gebruikt voor zeer gevoelige teams en bestanden. Alleen leden van jouw organisatie en gasten die je hebt gespecificeerd, kunnen bestanden met dit label ontsleutelen. Als je de machtigingen verder wilt isoleren zodat alleen leden van een specifiek team bestanden kunnen ontsleutelen, raadpleegt je [Een team implementeren met beveiligingsisolatie](secure-teams-security-isolation.md).

De zeer gevoelige laag biedt de volgende extra bescherming bovenop de basislaag:

- Een gevoeligheidslabel voor het team waarmee je het delen van gasten kunt in- of uitschakelen en de toegang tot SharePoint-inhoud beperkt voor onbeheerde apparaten. Dit label kan ook worden gebruikt om bestanden te classificeren en te versleutelen.
- Een meer beperkend standaardkoppelingstype voor delen
- Alleen teameigenaren kunnen privé-kanalen maken.
- Toegangsaanvragen voor de gekoppelde SharePoint-site zijn uitgeschakeld.

## <a name="guest-sharing"></a>Gasten delen

Afhankelijk van de aard van uw bedrijf, wilt u het delen met gasten mogelijk niet inschakelen voor teams die zeer gevoelige gegevens bevatten. Als u van plan bent om met personen buiten uw organisatie samen te werken in het team, raden we aan om delen met gasten in te schakelen. Microsoft 365 bevat diverse functies voor beveiliging en compliance waarmee u vertrouwelijke inhoud veilig kunt delen. Dit is over het algemeen een veiliger optie dan inhoud rechtstreeks naar mensen buiten uw organisatie te e-mailen.

Voor meer informatie over delen met gasten kunt u de volgende bronnen raadplegen:

- [Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen buiten uw organisatie](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [Een beveiligde omgeving voor het delen met gasten maken](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

Om delen met gasten toe te staan of te blokkeren, gebruiken we een combinatie van een gevoeligheidslabel voor het team en besturingselementen voor delen op siteniveau voor de bijbehorende SharePoint-site, die beide later worden besproken.

## <a name="sensitivity-labels"></a>Gevoeligheidslabels

Voor het zeer gevoelige beveiligingsniveau wordt een gevoeligheidslabel gebruikt om het team te classificeren. Dit label kan ook worden gebruikt om afzonderlijke bestanden in deze of andere teams te classificeren en te versleutelen, of in andere bestandslocaties zoals SharePoint of OneDrive. 

Als eerste stap moet u gevoeligheidslabels voor Teams inschakelen. Zie [Gevoeligheidslabels gebruiken om inhoud te beveiligen in Microsoft Teams, Office 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) voor meer informatie.

Als u al gevoeligheidslabels in uw organisatie hebt geïmplementeerd, kunt u overwegen hoe dit label past in uw algemene labelstrategie. U kunt de naam of instellingen zo nodig wijzigen om tegemoet te komen aan de behoeften van uw organisatie.

Wanneer u gevoeligheidslabels voor Teams hebt ingeschakeld, is de volgende stap het maken van het label.

Een gevoeligheidslabel maken
1. Open het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com).
2. Klik onder **Oplossingen** op **Informatiebeveiliging**.
3. Klik op **Een label maken**.
4. Geef een naam op voor het label. We suggereren **Zeer gevoelig**, maar u kunt een andere naam kiezen als die al in gebruik is.
5. Voeg een weergavenaam en een beschrijving toe en klik vervolgens op **Volgende**.
6. Selecteer op de **pagina Het bereik voor dit label definiëren** de opties **Bestanden en e-mailberichten** en **Groepen en sites** en klik op **Volgende**.
7. Selecteer op de pagina **Beveiligingsinstellingen voor bestanden en e-mailberichten kiezen** de optie **Bestanden en e-mailberichten versleutelen** en klik vervolgens op **Volgende**.
8. Kies op de pagina **Versleuteling** de optie **Versleutelingsinstellingen configureren**.
9. Klik onder **Machtigingen toewijzen aan specifieke gebruikers en groepen** op **Machtigingen toewijzen**.
10. Klik op **Alle gebruikers en groepen in uw organisatie toevoegen**.
11. Als gastgebruikers machtigingen voor het ontsleutelen van bestanden moeten hebben, klikt u op **Gebruikers of groepen toevoegen** en voegt u ze toe.
12.  Klik op **Opslaan** en klik vervolgens op **Volgende**.
13. Klik op de pagina *Automatische labeling voor bestanden en e-mailberichten* op **Volgende**.
14. Selecteer op de pagina **Beveiligingsinstellingen voor groepen en sites definiëren** de opties **Instellingen voor privacy en toegang voor externe gebruikers** en **Instellingen voor toegang tot apparaten en instellingen voor extern delen** en klik op **Volgende**.
15. Selecteer op de pagina **Instellingen voor privacy en toegang voor externe gebruikers definiëren** onder **Privacy** de optie **Privé**.
16. Als je gasttoegang wilt toestaan, selecteer je onder **Toegang voor externe gebruikers** de optie **Laat Microsoft 365-groepseigenaren personen van buiten de organisatie als gast aan de groep toevoegen**.
17. Klik op **Volgende**.
18. Selecteer op de pagina **Instellingen voor extern delen en instellingen voor toegang tot het apparaat definiëren** de optie **Extern delen beheren via gelabelde SharePoint-sites**.
19. Onder **Inhoud kan worden gedeeld met** kies je **Nieuwe en bestaande gasten** als je gasttoegang wilt toestaan of **Alleen personen binnen uw organisatie** als je dat niet wilt.
20. Kies onder **Toegang tot niet-beheerde apparaten** de optie **Toegang blokkeren**. (Als u gasten toelaat die geen beheerde apparaten hebben, kan het een goed idee zijn om de optie **Beperkte toegang via het web toestaan** te kiezen.)
21. Klik op **Volgende**.
22. Klik op de pagina **Automatische labeling voor databasekolommen** op **Volgende**.
23. Klik op **Label maken** en klik vervolgens op **Gereed**.

Nadat u het label heeft gemaakt, moet u het publiceren voor de gebruikers die het zullen gebruiken. Voor gevoelige bescherming maken we het label beschikbaar voor alle gebruikers. U kunt het label publiceren in het Microsoft 365-compliancecentrum, op het tabblad **Labelbeleid** op de pagina **Informatiebeveiliging**. Als u een bestaand beleid hebt dat van toepassing is op alle gebruikers, kunt u dit label toevoegen aan dat beleid. Als u een nieuw beleid wilt maken, raadpleegt u [Gevoeligheidslabels publiceren door een labelbeleid te maken](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="create-a-team"></a>Een team maken

Verdere configuratie van het zeer gevoelige scenario wordt uitgevoerd op de SharePoint-site die aan het team is gekoppeld, dus de volgende stap is het maken van een team.

Een team maken voor zeer vertrouwelijke informatie
1. Klik links in Teams op **Teams** en klik onderaan de lijst met teams op **Deelnemen aan een team of een team maken**.
2. Klik op **Team maken** (eerste kaart, linkerbovenhoek).
3. Kies **Een volledig nieuw team maken**.
4. Kies in de lijst **Gevoeligheid** het label **Zeer gevoelig** dat u zojuist hebt gemaakt.
5. Klik onder **Privacy** op **Privé**.
6. Typ een naam voor het team en klik vervolgens op **Maken**.
7. Voeg gebruikers toe aan het team en klik vervolgens op **sluiten**.

## <a name="private-channel-settings"></a>Instellingen voor privékanaal

In deze fase wordt u aangeraden het maken van privé-kanalen tot teameigenaren te beperken.

Het maken van een persoonlijk kanaal beperken
1. In het team klikt u op **Meer opties** en klikt u vervolgens op **Team beheren**.
2. Vouw op het tabblad **Instellingen** de optie **Machtigingen voor leden** uit.
3. Schakel het selectievakje **Leden toestaan privékanalen te maken** uit.

U kunt ook [teambeleid](https://docs.microsoft.com/MicrosoftTeams/teams-policies) gebruiken om te bepalen wie persoonlijke kanalen kan maken.

## <a name="sharepoint-settings"></a>SharePoint-instellingen

Telkens wanneer u een nieuw team met het zeer gevoelige label maakt, moet u twee stappen uitvoeren in SharePoint:

- Werk de instellingen voor het delen met gasten voor de site in het SharePoint-beheercentrum bij zodat deze overeenkomen met wat u hebt gekozen toen u het label maakte, en werk de standaardkoppeling voor delen bij naar *Personen met bestaande toegang*.
- Werk de instellingen voor het delen van sites op de site zelf bij om te voorkomen dat leden bestanden, mappen of de site delen, en schakel toegangsaanvragen uit.

### <a name="site-guest-sharing-settings"></a>Standaardinstellingen voor het delen van een site met een gast

De instelling voor het delen met gasten die u hebt gekozen toen u het label maakte (die alleen van invloed is op het teamlidmaatschap), moet als volgt overeenkomen met de instellingen voor het delen met gasten voor de bijbehorende SharePoint-site:

|Labelinstelling|Instelling voor een SharePoint-site|
|:------------|:----------------------|
|**Laat Office 365-groepseigenaren mensen buiten de organisatie toevoegen aan de groep** geselecteerd|**Nieuwe en bestaande gasten** (standaard voor nieuwe teams)|
|**Laat Office 365-groepseigenaren mensen buiten de organisatie toevoegen aan de groep** niet geselecteerd|**Alleen personen binnen uw organisatie**|

Site-instellingen bijwerken
1. Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).
2. Klik onder **Sites** op **Actieve sites**.
3. Klik op de site die is gekoppeld aan het team.
4. Klik op het tabblad **Beleid** onder **Extern delen** op **Bewerken**.
5. Als u de functie delen met gasten hebt toegestaan tijdens het maken van het zeer gevoelige label, moet u ervoor zorgen dat **Nieuwe en bestaande gasten** is geselecteerd. Als u delen niet hebt toegestaan toen u het label maakte, kiest u **Alleen mensen in uw organisatie**.
6. Schakel onder Standaard koppelingstype voor delen het selectievakje **Hetzelfde als instelling op organisatieniveau** uit en selecteer **Personen met bestaande toegang**.
7. Klik op **Opslaan**.

Als u dit wilt scripten als onderdeel van het proces voor het maken van een team, kunt u [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) gebruiken met de volgende parameters:

- `-SharingCapability Disabled` om delen met gasten uit te schakelen (deze is standaard ingeschakeld)
- `-DefaultSharingLinkType Internal` om de standaard koppeling voor delen te wijzigen in *specifieke personen*

#### <a name="private-channels"></a>Privékanalen

Als u privékanalen aan het team toevoegt, maakt elk privékanaal een nieuwe SharePoint-site met de standaardinstellingen voor delen. Deze sites zijn niet zichtbaar in het SharePoint-beheercentrum, dus u moet de PowerShell-cmdlet Set-SPOSite gebruiken om de instellingen voor het delen van gasten bij te werken.

### <a name="site-sharing-settings"></a>Standaardinstellingen voor het delen van een site

Om ervoor te zorgen dat de SharePoint-site niet wordt gedeeld met personen die geen deel uitmaken van het team, beperken we het delen ervan tot eigenaren. We beperken ook het delen van bestanden en mappen tot de teameigenaren. Dit helpt ervoor te zorgen dat eigenaren weten wanneer een bestand wordt gedeeld met iemand buiten het team.

Om het delen van sites met eigenaren te configureren
1. Ga in Teams naar het tabblad **Algemeen** van het team dat u wilt bijwerken.
2. Klik op de werkbalk van het team op **Bestanden**.
3. Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.
4. Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.
5. Klik in het deelvenster **Site-machtigingen** onder **Delen van een site** op **Wijzigen hoe leden kunnen delen**.
6. Kies onder **Machtigingen voor delen**, **Alleen site-eigenaren kunnen bestanden, mappen en de site delen**.
7. Schakel **Toegangsaanvragen toestaan** **Uit** en klik vervolgens op **Opslaan**.

## <a name="see-also"></a>Zie ook

[Gevoeligheidslabels en hun beleid maken en configureren](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)

