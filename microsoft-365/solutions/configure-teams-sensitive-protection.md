---
title: Teams met bescherming voor vertrouwelijke gegevens configureren
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
description: Informatie over het implementeren van teams met bescherming voor vertrouwelijke gegevens.
ms.openlocfilehash: 6c3d79e212a1a0333a7262b72ae0f1db8597096f
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002679"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a>Teams met bescherming voor vertrouwelijke gegevens configureren

In dit artikel kijken we naar het opzetten van een team met een gevoelig beschermingsniveau. Zorg ervoor dat u de stappen hebt voltooid in [teams implementeren met basisbeveiliging](configure-teams-baseline-protection.md) voordat u de stappen in dit artikel uitvoert. De gevoelige laag biedt de volgende extra bescherming boven op de basislaag:

- Een gevoeligheidslabel voor het team waarmee u het delen van gasten kunt in- of uitschakelen en de toegang tot SharePoint-inhoud beperkt tot alleen-internet voor onbeheerde apparaten. Dit label kan ook worden gebruikt om bestanden te classificeren.
- Een meer beperkend standaardkoppelingstype voor delen
- Alleen teameigenaren kunnen persoonlijke kanalen maken.

## <a name="guest-sharing"></a>Delen met gasten

Afhankelijk van de aard van uw bedrijf, wilt u het delen met gasten mogelijk niet inschakelen voor teams die gevoelige gegevens bevatten. Als u van plan bent om met personen buiten uw organisatie samen te werken in het team, raden we aan om delen met gasten in te schakelen. Microsoft 365 bevat diverse functies voor beveiliging en compliance waarmee u vertrouwelijke inhoud veilig kunt delen. Dit is over het algemeen een veiliger optie dan inhoud rechtstreeks naar mensen buiten uw organisatie te e-mailen.

Voor meer informatie over delen met gasten kunt u de volgende bronnen raadplegen:

- [Het beperken van de onopzettelijke blootstelling van bestanden bij het delen met personen buiten uw organisatie](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [Een beveiligde omgeving voor het delen met gasten maken](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

Om delen met gasten toe te staan of te blokkeren, gebruiken we een combinatie van een gevoeligheidslabel voor het team en besturingselementen voor delen op siteniveau voor de bijbehorende SharePoint-site, die beide later worden besproken.

## <a name="sensitivity-labels"></a>Gevoeligheidslabels

Voor het gevoelige beveiligingsniveau wordt een gevoeligheidslabel gebruikt om het team te classificeren. Dit label kan ook worden gebruikt om afzonderlijke bestanden in deze of andere teams te classificeren, of in andere bestandslocaties zoals SharePoint of OneDrive. 

Als eerste stap moet u gevoeligheidslabels voor Teams inschakelen. Zie [gevoeligheidslabels gebruiken om inhoud te beveiligen in Microsoft Teams, Office 365-groepen en SharePoint-sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) voor meer informatie.

Als u al gevoeligheidslabels in uw organisatie hebt geïmplementeerd, kunt u overwegen hoe dit label past in uw algemene labelstrategie. U kunt de naam of instellingen zo nodig wijzigen om tegemoet te komen aan de behoeften van uw organisatie.

Wanneer u gevoeligheidslabels voor Teams hebt ingeschakeld, is de volgende stap het maken van het label.

Een gevoeligheidslabel maken
1. Open het [Microsoft 365-compliancecentrum](https://compliance.microsoft.com).
2. Klik onder **Oplossingen**op **informatiebeveiliging**.
3. Klik op **een label maken**.
4. Geef een naam op voor het label. We suggereren **gevoelig**, maar u kunt een andere naam kiezen als die al in gebruik is.
5. Voeg een knopinfo toe en klik vervolgens op **volgende**.
6. Klik op de pagina **versleuteling** op **volgende**.
7. Schakel op de pagina **inhoudsmarkering** de optie inhoudsmarkering in als u automatisch een koptekst, voettekst of watermerk wilt toevoegen aan bestanden die met dit label worden geclassificeerd.
8. Stel op de pagina **Site- en groepsinstellingen** de **Site- en groepsinstellingen** in op **Aan**.
9. Klik in de vervolgkeuzelijst **privacy van Office 365 met de groep verbonden teamsites** op **privé - alleen leden hebben toegang tot de site**.
10. Als u gasttoegang wilt toestaan, selecteert u het selectievakje **laat groepseigenaren van Office 365 gebruikers buiten de organisatie toevoegen aan de groep**. 
11. Kies onder **niet-beheerde apparaten**de optie **beperkte toegang tot het Internet toestaan**.
12. Klik op **Volgende**.
13. Klik op de pagina **automatische labeling voor Office-apps** op **volgende**.
14. Klik op **Verzenden** en klik vervolgens op **Gereed**.

Nadat u het label heeft gemaakt, moet u het publiceren voor de gebruikers die het zullen gebruiken. Voor gevoelige bescherming maken we het label beschikbaar voor alle gebruikers. U kunt het label publiceren in het Microsoft 365-compliancecentrum, op het tabblad **labelbeleid** op de pagina **informatiebeveiliging**. Als u een bestaand beleid hebt dat van toepassing is op alle gebruikers, kunt u dit label toevoegen aan dat beleid. Als u een nieuw beleid wilt maken, raadpleegt u [gevoeligheidslabels publiceren door een labelbeleid te maken](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="create-a-team"></a>Een team maken

Verdere configuratie van het gevoelige scenario wordt uitgevoerd op de SharePoint-site die aan het team is gekoppeld, dus de volgende stap is het maken van een team.

Een team maken voor vertrouwelijke informatie
1. Klik links in Teams op **Teams** en klik onderaan de lijst met teams op **Deelnemen aan een team of een team maken**.
2. Klik op **team maken** (eerste kaart, linkerbovenhoek).
3. Kies **Een volledig nieuw team maken**.
4. Kies in de lijst **gevoeligheid** het label **gevoelig** dat u zojuist hebt gemaakt.
5. Klik onder **privacy** op **persoonlijk**.
6. Typ een naam voor het team en klik vervolgens op **maken**.
7. Voeg gebruikers toe aan het team en klik vervolgens op **sluiten**.

## <a name="private-channel-settings"></a>Instellingen voor privékanaal

In deze fase wordt u aangeraden het maken van persoonlijke kanalen tot teameigenaren te beperken.

Het maken van een persoonlijk kanaal beperken
1. In het team klikt u op **meer opties**en klikt u vervolgens op **team beheren**.
2. Vouw op het tabblad **Instellingen** de optie ** machtigingen voor leden** uit.
3. Schakel het selectievakje **Leden toestaan privékanalen te maken** uit.

U kunt ook [teambeleid](https://docs.microsoft.com/MicrosoftTeams/teams-policies) gebruiken om te bepalen wie persoonlijke kanalen kan maken.

## <a name="sharepoint-settings"></a>SharePoint-instellingen

Telkens wanneer u een nieuw team met het gevoelige label maakt, moet u twee stappen uitvoeren in SharePoint:

- Werk de instellingen voor het delen met gasten voor de site in het SharePoint-beheercentrum bij zodat deze overeenkomen met wat u hebt gekozen toen u het label maakte, en werk de standaardkoppeling voor delen bij naar *specifieke personen*.
- Werk de instellingen voor het delen van sites op de site zelf bij om te voorkomen dat leden de site delen.

### <a name="site-guest-sharing-settings"></a>Standaardinstellingen voor het delen van een site met een gast

De instelling voor het delen met gasten die u hebt gekozen toen u het label maakte (die alleen van invloed is op het teamlidmaatschap), moet als volgt overeenkomen met de instellingen voor het delen met gasten voor de bijbehorende SharePoint-site:

|Labelinstelling|Instelling voor een SharePoint-site|
|:------------|:----------------------|
|**Laat Office 365-groepseigenaren mensen buiten de organisatie toevoegen aan de groep** geselecteerd|**Nieuwe en bestaande gasten** (standaard voor nieuwe teams)|
|**Laat Office 365-groepseigenaren mensen buiten de organisatie toevoegen aan de groep** niet geselecteerd|**Alleen personen binnen uw organisatie**|

Site-instellingen bijwerken
1. Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).
2. Klik onder **sites**op **actieve sites**.
3. Klik op de site die is gekoppeld aan het team.
4. Klik op het tabblad **Beleid** onder **Extern delen** op **Bewerken**.
5. Als u de functie delen met gasten hebt toegestaan tijdens het maken van het gevoelige label, moet u ervoor zorgen dat **nieuwe en bestaande gasten** is geselecteerd. Als u delen niet hebt toegestaan toen u het label maakte, kiest u **Alleen mensen in uw organisatie**.
6. Schakel onder Standaard koppelingstype voor delen het selectievakje **hetzelfde als instelling op organisatieniveau** uit en selecteer **specifieke personen (alleen de personen die door de gebruiker worden opgegeven)**.
7. Klik op **Opslaan**.

Als u dit wilt scripten als onderdeel van het proces voor het maken van een team, kunt u [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) gebruiken met de volgende parameters:

- `-SharingCapability Disabled` om delen met gasten uit te schakelen (deze is standaard ingeschakeld)
- `-DefaultSharingLinkType Internal` om de standaard koppeling voor delen te wijzigen in *specifieke personen*

#### <a name="private-channels"></a>Privékanalen

Als u privékanalen aan het team toevoegt, maakt elk privékanaal een nieuwe SharePoint-site met de standaardinstellingen voor delen. Deze sites zijn niet zichtbaar in het SharePoint-beheercentrum, dus u moet de PowerShell-cmdlet Set-SPOSite gebruiken om de instellingen voor het delen van gasten bij te werken.

### <a name="site-sharing-settings"></a>Standaardinstellingen voor het delen van een site

Om ervoor te zorgen dat de SharePoint-site niet wordt gedeeld met personen die geen deel uitmaken van het team, beperken we het delen ervan tot eigenaren.

Om het delen van sites voor alleen-eigenaren te configureren
1. Ga in Teams naar het tabblad **algemeen** van het team dat u wilt bijwerken.
2. Klik op de werkbalk van het team op **Bestanden**.
3. Klik op het beletselteken en klik vervolgens op **Openen in SharePoint**.
4. Klik op de werkbalk van de onderliggende SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.
5. Klik in het deelvenster Site-machtigingen, onder **Instellingen voor delen** op **Instellingen voor delen wijzigen**.
6. Selecteer onder **machtigingen voor delen** de optie **site-eigenaren en leden, en personen met machtigingen voor bewerken kunnen bestanden en mappen delen, maar alleen site-eigenaren kunnen de site delen** en klik vervolgens op **opslaan**.


## <a name="see-also"></a>Zie ook

[Gevoeligheidslabels en hun beleid maken en configureren](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)


