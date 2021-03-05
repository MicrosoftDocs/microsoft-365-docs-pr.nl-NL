---
title: Microsoft Defender voor Office 365 evalueren
description: Met Defender voor Office 365 in evaluatiemodus maakt u e-mailbeleidsregels van Defender voor Office 365 die worden beoordeeld met malware, zoals malware, maar die niet op berichten reageren.
keywords: Office 365, Microsoft Defender voor Office 365, evaluatie van Office 365, office 365, Microsoft Defender, ATP evalueren
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1a9bf9461e8cf6d62e4283c9112b801371242f2e
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453703"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Microsoft Defender voor Office 365 evalueren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Evaluatie van Microsoft Defender voor Office 365 is een openbare previewversie. Deze preview-versie wordt geleverd zonder serviceovereenkomst. Bepaalde functies worden mogelijk niet ondersteund of hebben beperkte mogelijkheden.

Door een uitgebreide beveiligingsproductevaluatie uit te voeren, kunt u weloverwogen beslissingen over upgrades en aankopen nemen. Het is een goed middel om de mogelijkheden van het beveiligingsproduct uit te proberen en te beoordelen hoe het uw team voor beveiligingsbewerkingen kan helpen bij hun dagelijkse taken.

De evaluatie-ervaring van Microsoft Defender voor [Office 365](office-365-atp.md) is ontworpen om de complexiteit van de configuratie van apparaten en omgevingen weg te werken, zodat u zich kunt concentreren op het evalueren van de mogelijkheden van de beveiligingsoplossing. Het geldt alleen voor e-mailbeveiliging en niet voor SharePoint, Office-clients zoals Word of Teams.

Als u nog geen licentie hebt die Microsoft Defender voor Office 365 ondersteunt, kunt u een gratis evaluatie van [30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) dagen starten en de mogelijkheden testen in het Office 365-beveiligings- &-compliancecentrum ( https://protection.office.com/homepage) . U geniet van de snelle manier van instellen en u kunt deze eenvoudig uitschakelen indien nodig.

## <a name="how-the-evaluation-works"></a>Hoe de evaluatie werkt

Met Defender voor Office 365 in evaluatiemodus maakt u e-mailbeleidsregels van Defender voor Office 365 die worden beoordeeld met malware, zoals malware, maar die niet op berichten reageren. Het is niet nodig om de configuratie van uw MX-record te wijzigen.

In de evaluatiemodus [worden veilige bijlagen,](atp-safe-attachments.md) [veilige koppelingen](atp-safe-links.md)en beleidsregels voor postvakintelligentie namens u ingesteld. [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Alle beleidsregels van Defender voor Office 365 worden op de achtergrond gemaakt in de modus Niet-afdwingen en zijn niet voor u zichtbaar.

Als onderdeel van de installatie wordt via de evaluatiemodus ook [enhanced filtering voor verbindingslijnen geconfigureerd.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Het verbetert de filternauwkeurigheid door ip-adres- en afzendergegevens te behouden, die anders verloren gaan als e-mail een e-mailbeveiligingsgateway (ESG) passeert vóór Defender voor Office 365. Verbeterd filteren voor connectors verbetert ook de filternauwkeurigheid voor uw bestaande Exchange Online Protection (EOP) antispam- en anti-phishingbeleid.

Met verbeterd filteren voor verbindingslijnen wordt de filternauwkeurigheid verbeterd, maar kan de bezorgbaarheid van bepaalde berichten worden gewijzigd als u een ESG voor Defender voor Office 365 hebt en op dit moment geen EOP-filtering overzeilt. De impact is beperkt tot EOP-beleid. MDO-beleid dat is ingesteld als onderdeel van de evaluatie, wordt gemaakt in de modus niet-afdwingen. Als u de potentiële productie-impact wilt minimaliseren, kunt u alle EOP-filters omzeilen door een transportregel te maken om het spamver vertrouwelijkheidsniveau in te stellen op -1. Zie [Het EAC gebruiken om een regel voor de e-mailstroom te](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)maken die de SCL van een bericht in stelt voor meer   informatie.

Wanneer de evaluatiemodus is ingesteld, wordt er dagelijks een rapport bijgewerkt met maximaal 90 dagen aan gegevens die de berichten kwantificeren die geblokkeerd zouden zijn als het beleid zou zijn geïmplementeerd (bijvoorbeeld verwijderen, verzenden naar ongewenste e-mail, quarantaine). Rapporten worden gegenereerd voor alle Defender voor Office 365- en EOP-detecties. Ze worden samengevoegd per detectietechnologie (bijvoorbeeld imitatie) en kunnen worden gefilterd op tijdbereik. Bovendien kunnen berichtrapporten op aanvraag worden gemaakt om aangepaste draairapporten te maken of om berichten diep te bekijken met Behulp van Bedreigingsverkenner.

Met de vereenvoudigde set-upervaring kunt u zich concentreren op:

- De evaluatie uitvoeren
- Een gedetailleerd rapport maken
- Het rapport analyseren voor actie
- Het evaluatieresultaat presenteren

## <a name="before-you-begin"></a>Voordat u begint

### <a name="licensing"></a>Licenties

Als u de evaluatie wilt openen, moet u voldoen aan de licentievereisten. De volgende licenties werken:

- Abonnement 1 voor Microsoft Defender voor Office 365
- Abonnement 2 voor Microsoft Defender voor Office 365
- Microsoft 365 E5, Microsoft 365 E5-beveiliging
- Office 365 E5

Als u niet een van deze licenties hebt, moet u een proeflicentie aanvragen.

#### <a name="trial"></a>Proefversie

Als u een proeflicentie voor Microsoft Defender voor Office 365 wilt aanvragen, moet u de rol factureringsbeheerder of **globale beheerder hebben.**  Vraag toestemming aan iemand met de rol van globale beheerder. [Meer informatie over abonnementen en licenties](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

Als u de juiste rol hebt, kunt u het beste een proeflicentie voor Microsoft Defender voor Office 365 (Abonnement 2) aanvragen in het Microsoft 365-beheercentrum door naar facturerings->-aankoopservices te gaan. De proefversie bevat een gratis proefversie van 30 dagen voor 25 licenties. [Krijg een proefversie voor Microsoft Defender voor Office 365 (Abonnement 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

U hebt een venster van 30 dagen met de evaluatie om geavanceerde bedreigingen te controleren en te rapporteren. U kunt ook een betaald abonnement kopen als u de volledige mogelijkheden van Defender voor Office 365 wilt.

### <a name="roles"></a>Rollen

Exchange Online-rollen zijn vereist voor het instellen van Defender voor Office 365 in evaluatiemodus.

- [Meer informatie over machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [Meer informatie over het toewijzen van beheerdersrollen](../../admin/add-users/assign-admin-roles.md)

De volgende rollen zijn nodig:

|Taak|Rol|
|---|---|
|Krijg een gratis proefversie of koop Microsoft Defender voor Office 365 (abonnement 2)|Rol factureringsbeheerder OF globale beheerdersrol|
|Evaluatiebeleid maken|Externe en geaccepteerde domeinenrol; Rol van beveiligingsbeheerder|
|Evaluatiebeleid bewerken|Externe en geaccepteerde domeinenrol; Rol van beveiligingsbeheerder|
|Evaluatiebeleid verwijderen|Externe en geaccepteerde domeinenrol; Rol van beveiligingsbeheerder |
|Evaluatierapport weergeven|Rol van beveiligingsbeheerder OF beveiligingslezer|
|


### <a name="enhanced-filtering"></a>Verbeterde filters

Uw exchange Online Protection-beleid, zoals bulksge zoveel mogelijk en spambeveiliging, blijft hetzelfde. Tijdens de evaluatie wordt echter verbeterde filtering voor connectors inschakelen, wat van invloed kan zijn op uw e-mailstroom en beleidsregels van Exchange Online Protection, tenzij u deze overgeslagen.

Door verbeterde filters voor connectors kunnen tenants beveiliging tegen spoofing gebruiken. Anti-spoofing wordt niet ondersteund als u een e-mailbeveiligingsgateway (ESG) gebruikt zonder uitgebreide filters voor connectors te hebben ingeschakeld.

### <a name="urls"></a>URL's

URL's worden gedetoneerd tijdens de e-mailstroom. Als u niet wilt dat specifieke URL's worden gedetoneerd, beheert u de lijst met toegestane URL's op de juiste manier. Zie [De lijst met tenants toestaan/blokkeren beheren](tenant-allow-block-list.md) voor meer informatie.

URL-koppelingen in de e-mailberichten worden niet terug wikkelen om de impact van de klant te verminderen.

### <a name="email-routing"></a>E-mailroutering

Bereid de bijbehorende gegevens voor die u nodig hebt om in te stellen hoe uw e-mail momenteel wordt doorgestuurd, inclusief de naam van de binnenkomende connector die uw e-mail doorgestuurd. Als u alleen Exchange Online Protection gebruikt, hebt u geen connector.  [Meer informatie over e-mailstroom en e-mailroutering](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Ondersteunde e-mailrouteringsscenario's zijn:

- **Externe partner en/of on-premises serviceprovider:** de binnenkomende connector die u wilt evalueren, maakt gebruik van een externe provider en/of u gebruikt een oplossing voor e-mailbeveiliging on-premises.
- **Alleen Microsoft Exchange Online Protection:** de tenant die u wilt evalueren gebruikt Office 365 voor e-mailbeveiliging en de Mail Exchange (MX)-record wijst naar Microsoft.

### <a name="email-security-gateway"></a>E-mailbeveiligingsgateway

Als u een externe e-mailbeveiligingsgateway (ESG) gebruikt, moet u de naam van de provider weten. Als u een ESG on-premises of niet-ondersteunde leverancier gebruikt, moet u de openbare IP-adressen voor de apparaten weten.

Ondersteunde externe partners zijn:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Tweedejaars
- Wordt dit voor u?
- Trend Micro

### <a name="scoping"></a>Een bereik maken

U kunt het bereik van de evaluatie beperkt tot een binnenkomende connector. Als er geen connector is geconfigureerd, kunnen beheerders met het evaluatiebereik gegevens verzamelen van alle gebruikers in uw tenant om Defender voor Office 365 te evalueren.

## <a name="get-started-with-the-evaluation"></a>Aan de slag met de evaluatie

Zoek de kaart met de evaluatieset-up van Microsoft Defender voor Office 365 in het office 365-beveiligings- & compliancecentrum (van drie https://protection.office.com/homepage) toegangspunten:

- Bedreigingsbeheer > Dashboard
- Bedreigingsbeheer > beleid
- Rapporten > Dashboard

## <a name="setting-up-the-evaluation"></a>De evaluatie instellen

Wanneer u de in te stellen stroom voor de evaluatie start, krijgt u twee routeringsopties. Afhankelijk van de e-mailrouterings- en evaluatiebehoeften van uw organisatie, kunt u selecteren of u een externe en/of on-premises serviceprovider of alleen Microsoft Exchange Online gebruikt.

- Als u een externe partner en/of on-premises serviceprovider gebruikt, moet u de naam van de leverancier selecteren in de vervolgkeuzelijst. Geef de andere connectorgerelateerde details op.

- Selecteer Microsoft Exchange Online als de MX-record naar Microsoft wijst en u een postvak van Exchange Online hebt.

Controleer uw instellingen en bewerk deze zo nodig. Selecteer vervolgens **Evaluatie maken.** Er wordt een bevestigingsbericht weergegeven om aan te geven dat de set-up is voltooid.

Uw evaluatierapport van Microsoft Defender voor Office 365 wordt één keer per dag gegenereerd. Het kan tot 24 uur duren voordat de gegevens zijn ingevuld.

### <a name="exchange-rules-optional"></a>Exchange-regels (optioneel)

Als u een bestaande gateway hebt, wordt in de evaluatiemodus uitgebreide filtering voor verbindingslijnen geactiveerd. Hiermee verbetert u de nauwkeurigheid van het filteren door het IP-adres van de binnenkomende afzender te wijzigen. Dit kan de filtereigenschappen wijzigen en als u Exchange Online Protection niet overzeilt, kan dit de bezorgbaarheid van bepaalde berichten wijzigen. In dit geval wilt u misschien tijdelijk geen filters gebruiken om de impact te analyseren. Als u dit wilt omzeilen, gaat u naar het Exchange-beheercentrum en maakt u een beleid van SCL -1 (als u dit nog niet hebt). Zie E-mailstroomregels (transportregels) in Exchange Online voor meer informatie over de regelonderdelen en de manier waarop deze werken.

## <a name="evaluate-capabilities"></a>Mogelijkheden evalueren

Nadat het evaluatierapport is gegenereerd, kunt u zien hoeveel geavanceerde bedreigingskoppelingen, geavanceerde bedreigingsbijlagen en potentiële imitaties zijn geïdentificeerd in de werkruimten voor e-mailberichten en samenwerking in uw organisatie.

Nadat de proefversie is verlopen, kunt u het rapport nog 90 dagen openen. Er worden echter geen gegevens meer verzameld. Als u Microsoft Defender voor Office 365 wilt blijven gebruiken nadat uw proefabonnement is verlopen, moet u een betaald abonnement voor Microsoft Defender voor [Office 365 kopen (abonnement 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

U kunt op elk **moment naar Instellingen** gaan om uw routering bij te werken of de evaluatie uitschakelen. U moet echter dezelfde procedure opnieuw doorlopen als u besluit de evaluatie voort te zetten nadat u deze hebt uitgeschakeld.

## <a name="provide-feedback"></a>Feedback geven

Uw feedback helpt ons om uw omgeving beter te beschermen tegen geavanceerde aanvallen. Deel uw ervaring en wee van productmogelijkheden en evaluatieresultaten.

Selecteer **Feedback geven om** ons te laten weten wat u vindt.
