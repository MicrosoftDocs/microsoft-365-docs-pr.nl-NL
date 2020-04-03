---
title: Office 365 Advanced Threat Protection
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 02/24/2020
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection omvat veilige bijlagen, veilige koppelingen, geavanceerde hulpmiddelen tegen phishing, rapportagehulpmiddelen en functies voor bedreigingsinformatie.
ms.openlocfilehash: aac4cb43386577851d74e424d6435d0c15762bab
ms.sourcegitcommit: 9afcc63b1a7e73f6946f67207337f10b71a5d7f3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/12/2020
ms.locfileid: "42808453"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) hebben. Zie [Geavanceerde Outlook.com-beveiliging voor Office 365-abonnees](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2) als u Outlook.com, Office 365 Home of Office 365 Personal gebruikt en u zoek informatie over veilige koppelingen of veilige bijlagen in Outlook.

## <a name="overview"></a>Overzicht

Office 365 ATP (Advanced Threat Protection) beschermt uw organisatie tegen kwaadwillende bedreigingen door e-mailberichten, koppelingen (URL’s) en hulpmiddelen voor samenwerking. ATP bevat onder meer:

- **[Beleid voor bedreigingsbeveiliging](#configure-atp-policies)**: definieer beleid voor bedreigingsbeveiliging om het juiste beveiligingsniveau in te stellen voor uw organisatie.

- **[Rapporten](#view-office-365-atp-reports)**: bekijk realtime rapporten om ATP-prestaties in uw organisatie te bewaken.

- **[Functies voor bedreigingsonderzoek en reacties](#use-threat-investigation-and-response-capabilities)**: gebruik toonaangevende hulpmiddelen om bedreigingen te onderzoeken, te doorgronden, te simuleren en te voorkomen.

- **[Mogelijkheden voor geautomatiseerd onderzoek en acties](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)**: bespaar tijd en moeite bij het onderzoeken en beperken van bedreigingen.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP-abonnement 1 en -abonnement 2

De volgende tabel bevat een overzicht van wat er is inbegrepen in elk abonnement.

|Office 365 ATP-abonnement 1 |Office 365 ATP-abonnement 2|
|---------|---------|
|Functies voor configuratie, beveiliging en detectie:<br/>- [Veilige bijlagen](atp-safe-attachments.md)<br/>- [Veilige koppelingen](atp-safe-links.md)<br/>- [ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md)<br/>- [Geavanceerde bescherming tegen phishing](atp-anti-phishing.md)<br/>- [Realtime detectie](threat-explorer.md)     |Functies van Office 365 ATP-abonnement 1<br/>--- plus ---<br/>Functies voor automatisering, onderzoek, herstel en onderwijs:<br/>- [Bedreigingsoverzichten](threat-trackers.md)<br/>- [Bedreigingsverkenner](threat-explorer.md)<br/>- [Geautomatiseerd onderzoek en acties](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>- [Aanvalssimulator](attack-simulator.md)|

- Office 365 ATP-abonnement 2 is inbegrepen in Office 365 E5, Office 365 A5 en Microsoft 365 E5.

- Office 365 ATP-abonnement 1 is inbegrepen in Microsoft 365 Business.

- Office 365 ATP-abonnement 1 en Office 365 ATP-abonnement 2 zijn elk beschikbaar als invoegtoepassing voor bepaalde abonnementen. Zie [Beschikbaarheid van functies in ATP-abonnementen](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Als uw huidige abonnement Office 365 ATP niet bevat, [neem dan contact op met de verkoopafdeling voor een proefabonnement](https://go.microsoft.com/fwlink/p/?LinkId=518644) en bekijk hoe ATP werkt voor uw organisatie.

## <a name="configure-atp-policies"></a>ATP-beleid configureren

Met Office 365 ATP kan het beveiligingsteam van uw organisatie beveiliging configureren door beleid te definiëren in het Office 365-beveiligings- en compliancecentrum (Ga naar [https://protection.office.com](https://protection.office.com) > **Threat management** > **Policy**).

> [!TIP]
> Zie [Beveiligen tegen bedreigingen](protect-against-threats.md) voor een kort overzicht van te definiëren beleid.

Het beleid dat wordt gedefinieerd voor uw organisatie bepaalt het gedrag en beveiligingsniveau voor vooraf gedefinieerde bedreigingen. Beleidsopties zijn bijzonder flexibel. Het beveiligingsteam van uw organisatie kan bijvoorbeeld verfijnde bedreigingsbeveiliging instellen op gebruikers-, organisatie-, ontvanger- en domeinniveau. Het is belangrijk regelmatig uw beleid te controleren, omdat er dagelijks nieuwe bedreigingen en uitdagingen bijkomen.

- **[Veilige bijlagen in ATP](atp-safe-attachments.md)**: biedt ‘zero-day’-bescherming om uw berichtensysteem te beveiligen, door e-mailbijlagen te controleren op schadelijke inhoud. Alle berichten en bijlagen die geen virus-/malwarehandtekening hebben, worden gerouteerd naar een speciale omgeving en vervolgens worden machine learning en analysetechnieken gebruikt om kwaadwillende inhoud te ontdekken. Als er geen verdachte activiteit wordt gevonden, wordt het bericht doorgestuurd naar het postvak. Zie [Beleid voor veilige bijlagen in ATP instellen in Office 365](set-up-atp-safe-attachments-policies.md) voor meer informatie.

- **[Veilige koppelingen in ATP ](atp-safe-links.md)**: biedt ‘time-of-click’-verificatie van URL’s in bijvoorbeeld e-mailberichten en Office-bestanden. De bescherming is continu en is van toepassing op uw berichten- en Office-omgeving. Koppelingen worden gescand op elke klik: veilige koppelingen blijven toegankelijk en schadelijke koppelingen worden dynamisch geblokkeerd. Zie [Beleid voor veilige koppelingen in ATP instellen in Office 365](set-up-atp-safe-links-policies.md) voor meer informatie.

- **[ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md)**: beschermt uw organisatie wanneer gebruikers samenwerken en bestanden delen door schadelijke bestanden in teamsites en documentbibliotheken te identificeren en te blokkeren. Zie [Office 365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

- **[ATP-bescherming tegen phishing](atp-anti-phishing.md)**: detecteert pogingen om uw gebruikers en aangepaste domeinen na te bootsen. Hiermee worden machine learning-modellen en geavanceerde vervalsingsdetectie-algoritmen toegepast om phishing-aanvallen te voorkomen. Zie [Office 365 ATP-antiphishing en -antiphishingbeleid instellen](set-up-anti-phishing-policies.md).

## <a name="view-office-365-atp-reports"></a>Office 365 ATP-rapporten bekijken

Office 365 ATP bevat onder meer een geavanceerd [rapportagedashboard](view-reports-for-atp.md) om uw ATP-prestaties te bewaken. U kunt het openen in het Beveiligings- en compliancecentrum bij **Rapporten** > **Dashboard**.

Rapporten worden in realtime bijgewerkt en voorzien u zo van de nieuwste inzichten. Deze rapporten bieden ook aanbevelingen en waarschuwen u tegen naderende bedreigingen. Vooraf gedefinieerde rapporten omvatten het volgende:

- [Bedreigingsverkenner (of realtime detecties)](threat-explorer.md)

- [Statusrapport risicobeveiliging](view-reports-for-atp.md#threat-protection-status-report)

- [ATP-bestandstyperapport](view-reports-for-atp.md#atp-file-types-report)

- [ATP-rapport over berichtverwerking](view-reports-for-atp.md#atp-message-disposition-report)

- ... en verschillende andere.

## <a name="use-threat-investigation-and-response-capabilities"></a>Functies gebruiken om bedreigingen te onderzoeken en erop te reageren

Office 365 ATP-abonnement 2 bevat de beste [hulpmiddelen voor bedreigingsonderzoek en reacties](office-365-ti.md) waarmee het beveiligingsteam van uw organisatie kwaadwillende aanvallen kan anticiperen, doorgronden en voorkomen.

- **[Bedreigingsoverzichten](threat-trackers.md)** bieden de nieuwste informatie over actuele cybersecurity-kwesties.  U kunt bijvoorbeeld informatie bekijken over de nieuwste malware en tegenmaatregelen nemen voordat het een echte bedreiging voor uw organisatie wordt. De beschikbare overzichten bevatten [Noteworthy-overzichten](threat-trackers.md#noteworthy-trackers), [Trending-overzichten](threat-trackers.md#trending-trackers), [Bijgehouden query’s](threat-trackers.md#tracked-queries) en [Opgeslagen query’s](threat-trackers.md#saved-queries).

- **[Bedreigingsverkenner (of realtime detecties)](threat-explorer.md)**(ook wel Verkenner genoemd) is een realtime rapport waarmee u recente bedreigingen kunt identificeren en analyseren. U kunt Verkenner configureren om gegevens weer te geven voor aangepaste perioden.

- Met **[Aanvalssimulator](attack-simulator.md)** kunt u realistische aanvalscenario’s in uw organisatie uitvoeren om kwetsbaarheden te identificeren. Er zijn simulaties van de huidige typen aanvallen beschikbaar, inclusief spear phishingaanvallen ‘credential harvest’ en ‘attachment’ en wachtwoordspray en beveiligingsaanvallen op wachtwoorden.

## <a name="save-time-with-automated-investigation-and-response"></a>Tijd besparen met geautomatiseerd onderzoek en acties

(**NIEUW!**) Wanneer u een potentiële cyberaanval onderzoekt is tijd van doorslaggevend belang. Hoe sneller u aanvallen kunt identificeren en beperken, hoe beter het is voor uw organisatie. Mogelijkheden voor [Geautomatiseerd onderzoek en acties](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) omvatten een aantal beveiligingsdraaiboeken die automatisch kunnen worden gestart, zoals wanneer een waarschuwing wordt geactiveerd, of handmatig, zoals vanaf een weergave in Verkenner. AIR kan uw beveiligingsteam tijd en moeite besparen bij het effectief en efficiënt beperken van bedreigingen. Zie [AIR in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) voor meer informatie.

## <a name="permissions-required-to-use-atp-features"></a>Vereiste machtigingen voor ATP-functies

U moet een passende rol zijn toegewezen om toegang te krijgen tot ATP-functies in het Beveiligings- en compliancecentrum. De volgende tabel bevat enkele voorbeelden:

|Rol of rollengroep|Informatiebronnen|
|---------|---------|
|Office 365-hoofdbeheerder (die kan worden toegewezen in Azure Active Directory of in het Office 365-beveiligings- en compliancecentrum) |[Informatie over beheerdersrollen in Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Beveiligingsbeheerder (die kan worden toegewezen in Azure Active Directory of in het Office 365-beveiligings- en compliancecentrum) |[Machtigingen voor beheerdersrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[Rapporten in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md)|
|Exchange Online Organization Management (die wordt toegewezen in Exchange Online)|[Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|Zoeken en opschonen (die wordt alleen toegewezen in het Office 365-beveiligings- en compliancecentrum) |[Machtigingen in het Beveiligings- en compliancecentrum](machtigingen-in-het-beveiligings-en-compliance-centrum.md|

Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="get-office-365-atp"></a>Office 365 ATP kopen

Office 365 ATP is inbegrepen in bepaalde abonnementen, zoals Microsoft 365 E5, Office 365 E5, Office 365 A5 en Microsoft 365 Business. Als uw abonnement niet beschikt over Office 365 ATP kunt u ATP-abonnement 1 of ATP-abonnement 2 als invoegtoepassing kopen bij bepaalde abonnementen. Zie de volgende bronnen voor meer informatie:

- [Beschikbaarheid van Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) voor een lijst met abonnementen waarin ATP-abonnementen zijn opgenomen.

- [De beschikbaarheid van functies in ATP-abonnementen](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) voor een lijst met functies in abonnement 1 en 2.

- [De juiste Office 365 ATP aanschaffen](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) om abonnementen te vergelijken en Office 365 ATP te kopen.

- [Een gratis proefversie starten](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Nieuwe functies in Office 365 ATP

Er worden continu nieuwe functies aan Office 365 ATP toegevoegd. Zie de volgende bronnen voor meer informatie:

- [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) biedt een lijst met nieuwe functies die in ontwikkeling zijn en worden geïmplementeerd.

- [Office 365 Advanced Threat Protection-servicebeschrijving](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) beschrijft de functies en beschikbaarheid in ATP-abonnementen.

## <a name="see-also"></a>Zie ook

- [Microsoft Threat Protection](../mtp/microsoft-threat-protection.md)

- [Geautomatiseerd onderzoek en acties (AIR) in Microsoft Threat Protection](../mtp/mtp-autoir.md)
