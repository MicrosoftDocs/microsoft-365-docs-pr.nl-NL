---
title: Microsoft Defender voor Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender voor Office 365 omvat veilige bijlagen, veilige koppelingen, geavanceerde hulpmiddelen tegen phishing, rapportagehulpmiddelen en functies voor bedreigingsinformatie.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eab7cdbed592975739fdcfa1089e6f7d2c25d880
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904114"
---
# <a name="microsoft-defender-for-office-365"></a>Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) hebben. Zie [Geavanceerde Outlook.com-beveiliging voor Microsoft 365-abonnees](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2) als u Outlook.com, Microsoft 365 Family of Microsoft 365 Personal gebruikt en u zoek informatie over veilige koppelingen of veilige bijlagen in Outlook.

Microsoft Defender voor Office 365 beschermt je organisatie tegen de kwaadaardige dreigingen van e-mailberichten, koppelingen (URL's) en samenwerkingsprogramma's. Defender voor Office 365 omvat:

- **[Beleid voor bedreigingsbeveiliging](#configure-microsoft-defender-for-office-365-policies)**: definieer beleid voor bedreigingsbeveiliging om het juiste beveiligingsniveau in te stellen voor uw organisatie.

- **[Rapporten](#view-microsoft-defender-for-office-365-reports)**: bekijk realtime rapporten om prestaties van Defender voor Office 365 in de organisatie te bewaken.

- **[Functies voor bedreigingsonderzoek en reacties](#use-threat-investigation-and-response-capabilities)**: gebruik toonaangevende hulpmiddelen om bedreigingen te onderzoeken, te doorgronden, te simuleren en te voorkomen.

- **[Mogelijkheden voor geautomatiseerd onderzoek en acties](office-365-air.md)**: bespaar tijd en moeite bij het onderzoeken en beperken van bedreigingen.

## <a name="interactive-guide-to-microsoft-defender-for-office-365"></a>Interactieve handleiding voor Microsoft Defender voor Office 365
In deze interactieve handleiding leer je hoe je je organisatie kunt beschermen met Microsoft Defender voor Office 365. Je ziet hoe je met behulp van Defender voor Office 365 je beveiligingsbeleid kunt definiëren, bedreigingen kunt analyseren voor je organisatie en kunt reageren op aanvallen.

[Bekijk de interactieve handleiding](https://aka.ms/MSDO-IG)

## <a name="getting-started"></a>Aan de slag

Als je nog niet eerder met Microsoft Defender voor Office 365 hebt gewerkt of als je *al doende* het beste leert, kun je er baat bij hebben om de initiële Defender voor Office 365-configuratie in segmenten op te delen en rapporten te bekijken met dit artikel als referentie. Hier vindt u logische segmenten van een vroege configuratie:

- Configureer alles met '*anti*' in de naam.
  - anti-malware
  - anti-phishing
  - anti-spam
- Configureer alles met '*veilig*' in de naam.
  - Veilige koppelingen
  - Veilige bijlagen
- De werkbelastingen verdedigen (bijv. SharePoint Online, OneDrive en Teams)
- Beschermen met Zero-Hour Auto Purge

[Klik op deze koppeling](protect-against-threats.md) om al doende te leren.

> [!NOTE]
> Er zijn twee verschillende typen abonnementen beschikbaar voor Microsoft Defender voor Office 365. U kunt zien of u **Abonnement 1** hebt als u 'Realtime detecties' hebt en **Abonnement 2** als u Bedreigingsverkenner hebt. Het abonnement dat u gebruikt, is van invloed op de hulpmiddelen die u ziet, dus zorg er bij het leren voor dat u weet welk abonnement u hebt.

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365

De volgende tabel bevat een overzicht van wat er is inbegrepen in elk abonnement.

****

|Abonnement 1 voor Microsoft Defender voor Office 365|Abonnement 2 voor Microsoft Defender voor Office 365|
|---|---|
|Functies voor configuratie, beveiliging en detectie: <ul><li>[Veilige bijlagen](safe-attachments.md)</li><li>[Veilige koppelingen](safe-links.md)</li><li>[Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Bescherming tegen phishing in Defender voor Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Detecties in realtime](threat-explorer.md)</li></ul>|Functies in abonnement 1 voor Microsoft Defender voor Office 365 <br>--- plus ---<br> Functies voor automatisering, onderzoek, herstel en onderwijs:<ul><li>[Bedreigingsoverzichten](threat-trackers.md)</li><li>[Bedreigingsverkenner](threat-explorer.md)</li><li>[Geautomatiseerd onderzoek en reactie](office-365-air.md)</li><li>[Aanvalssimulator](attack-simulator.md)</li><li>[Campagneweergaven](campaigns.md)</li></ul>|
|

- Abonnement 2 voor Microsoft Defender voor Office 365 is inbegrepen in Office 365 E5, Office 365 A5, Microsoft 365 E5 Security en Microsoft 365 E5.

- Abonnement 1 voor Microsoft Defender voor Office 365 is inbegrepen in Microsoft 365 Business Premium.

- Abonnement 1 voor Microsoft Defender voor Office 365 en abonnement 2 voor Microsoft Defender voor Office 365 zijn elk beschikbaar als een invoegtoepassing voor bepaalde abonnementen. Raadpleeg voor meer informatie [Beschikbaarheid van functies in Microsoft Defender voor Office 365-abonnementen](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- De functie [Veilige documenten](safe-docs.md) is alleen beschikbaar voor gebruikers met een Microsoft 365 E5- of Microsoft 365 E5 Security-licentie (niet opgenomen in abonnementen voor Microsoft Defender voor Office 365).

- Als je huidige abonnement Microsoft Defender voor Office 365 niet bevat, [neem dan contact op met de verkoopafdeling voor een proefabonnement](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) en bekijk hoe Defender voor Office 365 werkt voor jouw organisatie.

## <a name="configure-microsoft-defender-for-office-365-policies"></a>Beleid in Microsoft Defender voor Office 365 instellen

Met Microsoft Defender voor Office 365 kan het beveiligingsteam van uw organisatie beveiliging configureren door beleid te definiëren in het Beveiligings- en compliancecentrum (Ga naar <https://protection.office.com> \> **Bedreigingsbeheer** \> **Beleid**).

Meer informatie vindt u in [deze video](https://www.youtube.com/watch?v=vivvTmWJ_3c). 

> [!TIP]
> Zie [Beveiligen tegen bedreigingen](protect-against-threats.md) voor een kort overzicht van te definiëren beleid.

## <a name="defender-for-office-365-policies"></a>Beleid voor Defender voor Office 365

Het beleid dat wordt gedefinieerd voor uw organisatie bepaalt het gedrag en beveiligingsniveau voor vooraf gedefinieerde bedreigingen. Beleidsopties zijn bijzonder flexibel. Het beveiligingsteam van uw organisatie kan bijvoorbeeld verfijnde bedreigingsbeveiliging instellen op gebruikers-, organisatie-, ontvanger- en domeinniveau. Het is belangrijk regelmatig uw beleid te controleren, omdat er dagelijks nieuwe bedreigingen en uitdagingen bijkomen.

- **[Veilige bijlagen](safe-attachments.md)**: biedt ‘zero-day’-bescherming om uw berichtensysteem te beveiligen, door e-mailbijlagen te controleren op schadelijke inhoud. Alle berichten en bijlagen die geen virus-/malwarehandtekening hebben, worden gerouteerd naar een speciale omgeving en vervolgens worden machine learning en analysetechnieken gebruikt om kwaadwillende inhoud te ontdekken. Als er geen verdachte activiteit wordt gevonden, wordt het bericht doorgestuurd naar het postvak. Zie [Beleid voor veilige bijlagen instellen](set-up-safe-attachments-policies.md) voor meer informatie.

- **[Veilige koppelingen](safe-links.md)**: biedt ‘time-of-click’-verificatie van URL’s in bijvoorbeeld e-mailberichten en Office-bestanden. De bescherming is continu en is van toepassing op uw berichten- en Office-omgeving. Koppelingen worden gescand op elke klik: veilige koppelingen blijven toegankelijk en schadelijke koppelingen worden dynamisch geblokkeerd. Zie [Beleid voor veilige koppelingen instellen](set-up-safe-links-policies.md) voor meer informatie.

- **[Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams](mdo-for-spo-odb-and-teams.md)**: beschermt uw organisatie wanneer gebruikers samenwerken en bestanden delen door schadelijke bestanden in teamsites en documentbibliotheken te identificeren en te blokkeren. Raadpleeg voor meer informatie [Defender voor Office 365 inschakelen voor SharePoint, OneDrive en Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

- **[Bescherming tegen phishing in Defender voor Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**: detecteert pogingen om je gebruikers en interne of aangepaste domeinen na te bootsen. Hiermee worden machine learning-modellen en geavanceerde vervalsingsdetectie-algoritmen toegepast om phishing-aanvallen te voorkomen. Raadpleeg voor meer informatie [Beleid tegen phishing configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md).

## <a name="view-microsoft-defender-for-office-365-reports"></a>Microsoft Defender voor Office 365-rapporten weergeven

Microsoft Defender voor Office 365 bevat een geavanceerd [rapportagedashboard](view-reports-for-mdo.md) voor het controleren van de prestaties van Defender voor Office 365. Je vindt het in het Beveiligings- en compliancecentrum bij **Rapporten**\>**Dashboard**.

Rapporten worden in realtime bijgewerkt en voorzien u zo van de nieuwste inzichten. Deze rapporten bieden ook aanbevelingen en waarschuwen u tegen naderende bedreigingen. Vooraf gedefinieerde rapporten omvatten het volgende:

- [Bedreigingsverkenner (of realtime detecties)](threat-explorer.md)

- [Statusrapport bedreigingsbeveiliging](view-reports-for-mdo.md#threat-protection-status-report)

- [Rapport over bestandstypen voor Defender voor Office 365](view-reports-for-mdo.md#defender-for-office-365-file-types-report)

- [Rapport over berichtverwerking voor Defender voor Office 365](view-reports-for-mdo.md#defender-for-office-365-message-disposition-report)

- ... en verschillende andere.

## <a name="use-threat-investigation-and-response-capabilities"></a>Functies gebruiken om bedreigingen te onderzoeken en erop te reageren

Abonnement 2 van Microsoft Defender voor Office 365 bevat de beste [hulpmiddelen voor bedreigingsonderzoek en reacties](office-365-ti.md) waarmee het beveiligingsteam van je organisatie kwaadwillende aanvallen kan anticiperen, doorgronden en voorkomen.

- **[Bedreigingsoverzichten](threat-trackers.md)** bieden de nieuwste informatie over actuele cybersecurity-kwesties.  U kunt bijvoorbeeld informatie bekijken over de nieuwste malware en tegenmaatregelen nemen voordat het een echte bedreiging voor uw organisatie wordt. De beschikbare overzichten bevatten [Noteworthy-overzichten](threat-trackers.md#noteworthy-trackers), [Trending-overzichten](threat-trackers.md#trending-trackers), [Bijgehouden query’s](threat-trackers.md#tracked-queries) en [Opgeslagen query’s](threat-trackers.md#saved-queries).

- **[Bedreigingsverkenner (of realtime detecties)](threat-explorer.md)**(ook wel Verkenner genoemd) is een realtime rapport waarmee u recente bedreigingen kunt identificeren en analyseren. U kunt Verkenner configureren om gegevens weer te geven voor aangepaste perioden.

- Met **[Aanvalssimulator](attack-simulator.md)** kunt u realistische aanvalscenario’s in uw organisatie uitvoeren om kwetsbaarheden te identificeren. Er zijn simulaties van de huidige typen aanvallen beschikbaar, inclusief spear phishingaanvallen ‘credential harvest’ en ‘attachment’ en wachtwoordspray en beveiligingsaanvallen op wachtwoorden.

## <a name="save-time-with-automated-investigation-and-response"></a>Tijd besparen met geautomatiseerd onderzoek en acties

(**NIEUW!**) Wanneer u een potentiële cyberaanval onderzoekt is tijd van doorslaggevend belang. Hoe sneller u aanvallen kunt identificeren en beperken, hoe beter het is voor uw organisatie. Mogelijkheden voor [Geautomatiseerd onderzoek en acties](office-365-air.md) (AIR) omvatten een aantal beveiligingsdraaiboeken die automatisch kunnen worden gestart, zoals wanneer een waarschuwing wordt geactiveerd, of handmatig, zoals vanaf een weergave in Verkenner. AIR kan uw beveiligingsteam tijd en moeite besparen bij het effectief en efficiënt beperken van bedreigingen. Zie [AIR in Office 365](office-365-air.md) voor meer informatie.

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a>Vereiste machtigingen voor het gebruik van de functies van Microsoft Defender voor Office 365

Er moet een in aanmerking komende rol aan jou zijn toegewezen om toegang te krijgen tot Microsoft Defender voor Office 365-functies in het Beveiligings- en compliancecentrum. De volgende tabel bevat enkele voorbeelden:

|Rol of rollengroep|Informatiebronnen|
|---|---|
|Globale beheerder (die kan worden toegewezen in Azure Active Directory of in het beveiligings- en compliancecentrum)|[Over Microsoft 365-beheersrollen](../../admin/add-users/about-admin-roles.md)|
|Beveiligingsbeheerder (die kan worden toegewezen in Azure Active Directory of in het beveiligings- en compliancecentrum)|[Machtigingen voor beheerdersrollen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [Rapporten in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md)|
|Exchange Online Organization Management (die wordt toegewezen in Exchange Online)|[Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|Zoeken en opschonen (die wordt alleen toegewezen in het beveiligings- en compliancecentrum)|[Machtigingen in het Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md)|

Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="get-microsoft-defender-for-office-365"></a>Download Microsoft Defender voor Office 365

Microsoft Defender voor Office 365 is inbegrepen in bepaalde abonnementen, zoals Microsoft 365 E5, Office 365 E5, Office 365 A5 en Microsoft 365 Business Premium. Als je abonnement geen Defender voor Office 365 bevat, kun je abonnement 1 voor Defender voor Office 365 of abonnement 2 voor Defender voor Office 365 aanschaffen als een invoegtoepassing voor bepaalde abonnementen. Zie de volgende bronnen voor meer informatie:

- [Beschikbaarheid van Microsoft Defender voor Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) voor een lijst met abonnementen waarin een abonnement voor Defender voor Office 365 is opgenomen.

- [De beschikbaarheid van functies in Microsoft Defender voor Office 365-abonnementen](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) voor een lijst met functies in abonnement 1 en 2.

- [De juiste Microsoft Defender voor Office 365 kiezen](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) voor het vergelijken van abonnementen en het aanschaffen van Defender voor Office 365.

- [Een gratis proefversie starten](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a>Nieuwe functies in Microsoft Defender voor Office 365

Er worden doorlopend nieuwe functies aan Microsoft Defender voor Office 365 toegevoegd. Zie de volgende bronnen voor meer informatie:

- [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=Microsoft%2CDefender%2Cfor%2COffice%2C365) biedt een lijst met nieuwe functies die in ontwikkeling zijn en worden geïmplementeerd.

- [Beschrijving van de service Microsoft Defender voor Office 365 ](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) beschrijft de functies en beschikbaarheid in de verschillende abonnementen voor Defender voor Office 365.

## <a name="see-also"></a>Zie ook

- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

- [Geautomatiseerde onderzoeken en reacties in Microsoft 365 Defender](../defender/m365d-autoir.md) 1
