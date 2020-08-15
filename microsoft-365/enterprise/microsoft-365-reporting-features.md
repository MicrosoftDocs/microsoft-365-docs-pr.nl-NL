---
title: Rapportagefuncties in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
f1.keywords:
- NOCSH
description: Meer informatie over diverse rapportfuncties in Microsoft 365, waaronder Azure Active Directory en Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 104d587ea87a61a66b73aa1441170f37e082a72f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689382"
---
# <a name="microsoft-365-reporting-features"></a>Rapportagefuncties in Microsoft 365

Rapportagefuncties in Microsoft 365 biedt diverse controlerapporten voor Azure Active Directory (Azure AD), Exchange Online, Apparaatbeheer, toezicht Beoordelingen voor de beheerder en preventie van gegevensverlies (DLP). Deze rapporten wijken af van de activiteitenrapporten van Microsoft 365.

## <a name="microsoft-365-reports-dashboard"></a>Microsoft 365 rapporten dashboard

Het Dashboard rapporten in de preview-versie van het Microsoft 365-Beheercentrum geeft gebruik activiteiten weer in Microsoft 365. Globale beheerders van Microsoft 365 of een beheerder van Exchange Online, SharePoint Online of Skype voor bedrijven kan granulair inzicht krijgen in het gebruik van de service. Het aantal gebruikers met een bepaalde Microsoft 365-service, zoals het aantal gebruikers dat Microsoft 365-apps voor Enterprise heeft geactiveerd (eerder met de naam Office 365 ProPlus), en de hoeveelheid e-mail die door de organisatie wordt doorgevoerd. Rapporten zijn beschikbaar voor de laatste 7, 30, 90 en 180 dagen.

De volgende rapporten zijn beschikbaar:

- [Rapport e-mail activiteit](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Rapport Microsoft Office-activeringen](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [Gebruiksrapport voor SharePoint Online-site](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [Rapport gebruik van OneDrive voor bedrijven](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Yammer-activiteitenoverzicht](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Skype voor bedrijven-rapport activiteit](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Rapport van peer-to-peer activiteit in Skype voor bedrijven](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Skype voor bedrijven-rapport Vergader activiteiten van organisator](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Skype voor bedrijven-rapport Vergader activiteiten van deelnemers](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

Zie [activiteitenoverzichten in het Microsoft 365-Beheercentrum](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)voor meer informatie.

## <a name="azure-ad-reports"></a>Azure AD-rapporten

Microsoft 365 maakt gebruik van Azure AD voor verificatie en identiteitsbeheer. Microsoft 365-beheerders gebruiken rapporten die worden gegenereerd door Azure om ongebruikelijke activiteit en toegang tot hun gegevens te identificeren. U kunt Access-en gebruiksrapporten in azure AD gebruiken om inzicht te krijgen in de Directory integriteit en beveiliging van uw organisatie. Met deze informatie kunt u mogelijke beveiligingsrisico's identificeren en verhelpen.

Azure AD-rapporten kunnen worden geëxporteerd naar Microsoft Excel en worden gecorreleerd met andere gegevens van Microsoft 365. De resultaten van een zoekopdracht in het auditlogboek kunnen bijvoorbeeld inzicht geven in toegang tot en op toepassingsniveau. De rapporten geavanceerde anomalie en Resourcegebruik zijn beschikbaar met Azure AD Premium. Met deze geavanceerde rapporten kunt u uw beveiliging Posture en helpen u te reageren op potentiële bedreigingen door analyses toe te passen over het openen van apparaten en toepassingsgebruik. Zie [Azure Active Directory-rapporten](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/)voor meer informatie.

## <a name="exchange-online-audit-reports"></a>Controlerapporten van Exchange Online

Controlerapporten van Exchange Online bevatten informatie over toegang tot het postvak en de wijzigingen die door beheerders zijn aangebracht in uw Exchange Online-Tenant. Met behulp van Postvak controle kunt u de taken in de volgende tabel gebruiken om rapporten uit te voeren en auditlogboeken van Exchange Online te exporteren.

> [!NOTE]
> U moet de controlelogboekregistratie voor uw postvak inschakelen voor elk postvak, zodat controlegebeurtenissen worden opgeslagen in het auditlogboek voor dat postvak. Als de logboekregistratie van het postvak niet is ingeschakeld voor een postvak, worden gebeurtenissen voor dat postvak niet opgeslagen in het auditlogboek en worden er geen controlerapporten voor de Postvak weergegeven. Zie voor meer informatie [Postvak controle inschakelen](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918).

| Taak | Beschrijving |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Een rapport voor toegang tot een postvak van een niet-eigenaar uitvoeren](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | Toont de lijst met postvakken die door iemand anders dan de eigenaar van het postvak worden geopend. Het rapport bevat informatie over de gebruikers die toegang hebben tot het postvak, de acties die ze hebben ondernomen in het postvak en of de acties succesvol zijn verlopen. |
| [Controlelogboeken voor Postvak exporteren](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | Controlelogboeken voor e-mail bevatten informatie over toegang en acties in een postvak dat is gemaakt door een andere gebruiker dan de eigenaar van het postvak. Beheerders kunnen postvakken en een datumbereik opgeven om rapporten te genereren. De logboeken worden geëxporteerd in XML, gekoppeld aan een bericht en naar specifieke gebruikers verzonden, zoals wordt bepaald door de beheerder. |
| [Een groep rollend groep van beheerders uitvoeren](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | De rollen groep beheerder wijst beheerdersbevoegdheden toe aan gebruikers. Met deze bevoegdheden kunnen gebruikersbeheertaken uitvoeren, zoals wachtwoorden opnieuw instellen, postvakken maken of wijzigen, en beheerdersmachtigingen toewijzen aan andere gebruikers. Het rapport rollen groep beheerder toont wijzigingen in rollen groepen, inclusief het toevoegen of verwijderen van leden. |
| [Het auditlogboek van de beheerder weergeven](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | De lijst controleverslag van de beheerder bevat alle functies Create, update en Delete die worden uitgevoerd door beheerders in Exchange Online. Logboekvermeldingen voeren informatie over de uitvoering van de cmdlet, de parameters die zijn gebruikt om de cmdlet uit te voeren en welke objecten werden beïnvloed. |
| [Inhoud van postvak zoeken en vasthouden](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | Dit onderwerp bevat informatie over wijzigingen in de instellingen voor eDiscovery-of in-place bewarings instellingen voor postvakken. |
| [Het auditlogboek van de beheerder exporteren](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | In het controlelogboek van de beheerder worden specifieke beheeracties vastgelegd, zoals Create, update en delete in Exchange Online. De resultaten van het logboek worden geëxporteerd naar XML en beheerders kunnen ervoor kiezen dit logboek naar een set gebruikers te verzenden. |
| [Een rapport in de wachtstand van een postvak in per postvak uitvoeren](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | Dit onderwerp bevat informatie over wijzigingen in de instellingen voor de instellingen voor rechtszaken in postvakken. |
| [Het auditlogboek voor externe beheerders weergeven en exporteren](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | Bevat details van bewerkingen die zijn uitgevoerd door externe beheerders. De vermeldingen geven informatie over welke cmdlet is uitgevoerd, welke parameters zijn gebruikt en acties die objecten maken, wijzigen of verwijderen in Exchange Online. |

## <a name="device-compliance-reports"></a>Rapporten over apparaatcompatibiliteit

U beheert en verveiligt mobiele apparaten die zijn verbonden met uw abonnement met behulp van het MDM (Mobile Device Management) van Microsoft 365. Mobiele apparaten die worden gebruikt om toegang te krijgen tot e-mail, agenda, contactpersonen en documenten speelt een belangrijk deel aan om ervoor te zorgen dat werknemers overal en overal kunnen werken. Het is belangrijk dat u de gegevens van uw organisatie beschermt. U gebruikt Microsoft 365 MDM om beveiligingsbeleid en toegangsregels voor apparaten in te stellen. Als u gaat verloren of gestolen, gebruikt u Microsoft 365 MDM ook om mobiele apparaten te wissen.

Nalevings rapporten van MDM bieden een overzicht van beleidsregels die door een organisatie zijn ingesteld voor het beveiligen van mobiele apparaten die toegang hebben tot gegevens van Microsoft 365. In het rapport kunt u apparaten filteren op nalevingsstatus, gerapporteerde overtredingen, geblokkeerde apparaten en het aantal apparaten dat wordt gewist als gevolg van beveiligingsbeleid. Zie voor meer informatie [overzicht van Mobile Device Management voor Microsoft 365](https://support.microsoft.com/office/overview-of-mobile-device-management-mdm-for-microsoft-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a).

## <a name="data-loss-prevention"></a>Preventie van gegevensverlies

DLP-beleid helpt bij het beheren van de beveiliging en de stroom van gegevens in een organisatie. U kunt beleidsregels instellen voor het blokkeren van toegang tot inhoud, gegevens versleutelen of gebruikers informeren over beleid en beleidsschendingen via de DLP-beleids tips van de toepassing. DLP-rapporten bieden inzicht in het aantal beleids overeenkomsten, overschrijvingen en onjuiste positieve waarden.

Met het Microsoft 365-Beheercentrum kunt u informatie weergeven over het aantal berichten dat is gedetecteerd door de DLP-beleidsregels. DLP-rapporten geven inzicht in beleid en regel overeenkomsten voor verzonden en ontvangen e-mail. U kunt ook het aantal resultaten, overschrijvingen en fout-positieven voor elk beleid bekijken via het Exchange-Beheercentrum. Als u een Excel-rapport downloadt, kunt u nog meer details weergeven, zoals wie het bericht heeft verzonden, op welke dag en welke beleids overeenkomsten zijn geactiveerd. Zie [rapporten weergeven over DLP-beleids detectie](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj889415(v=exchg.150))voor meer informatie.

## <a name="auditing-in-yammer-enterprise"></a>Controleren in Yammer Enterprise

Yammer Enterprise biedt beheerders de mogelijkheid gegevens van gebruikersactiviteit vanuit hun Yammer-netwerk te exporteren via de [Data export-API voor Yammer](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2), of handmatig via de pagina Yammer-netwerkbeheerder. De mogelijkheid voor het exporteren van Logboeken is beperkt tot netwerkbeheerders in Yammer. (Alle globale beheerders van Microsoft 365 zijn Yammer-netwerkbeheerders.)

De volgende gegevens zijn exporteerbaar:

| Namen | Beschrijving |
|----------------------------|-------------------------------------------------------------------------|
| Users.csv | Alle nieuwe, in behandeling zijnde en geschorste gebruikers in het netwerk |
| Messages.csv | Alle berichten in het netwerk |
| Files.csv (metagegevens) | Metagegevens, zoals naam, URL van de API, Uploader-ID, geüpload op, etc. |
| Files.csv (oorspronkelijke bestanden) | Zip-bestand van de oorspronkelijke bestanden die zijn geüpload door gebruikers naar Yammer |
| Topics.csv | Onderwerpen die in het netwerk zijn gemaakt |
| Pages.csv | Pagina's (notities) die zijn gemaakt door gebruikers in het netwerk |
| Admins.csv | Alle geverifieerde beheerders in het netwerk |
| Networks.csv | Alle externe Yammer-netwerken |

Yammer Enterprise-gegevens is ook beschikbaar via de activiteitenrapporten van Microsoft 365. Daarnaast werkt Yammer actief samen aan een extra logboekregistratie via de API van Microsoft 365 Management Activity en over de mogelijkheid om gegevens te verbeteren met Power BI. Zie het overzicht van [Office](https://fasttrack.microsoft.com/roadmap?filters=yammer) voor meer informatie over deze functies.
