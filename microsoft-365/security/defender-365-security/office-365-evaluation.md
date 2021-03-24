---
title: Microsoft Defender voor Office 365 evalueren
description: Defender voor Office 365 maakt in de evaluatiemodus Defender voor Office 365-e-mailbeleid waarin vonnissen, zoals malware, worden logboeken, maar die geen actie ondernemen op berichten.
keywords: evaluatie van Office 365, Microsoft Defender voor Office 365, evaluatie van Office 365, office 365, Microsoft Defender, ATP proberen
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
ms.openlocfilehash: 2e97e510cbc3188f8cc6117c5d7bd1e1d23897eb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058866"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Microsoft Defender voor Office 365 evalueren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> De evaluatie van Microsoft Defender voor Office 365 is openbaar. Deze preview-versie wordt geleverd zonder een serviceovereenkomst. Bepaalde functies worden mogelijk niet ondersteund of hebben mogelijk beperkte mogelijkheden.

Door een uitgebreide beveiligingsproductevaluatie uit te voeren, kunt u weloverwogen beslissingen nemen over upgrades en aankopen. Het helpt om de mogelijkheden van het beveiligingsproduct uit te proberen om te beoordelen hoe het uw beveiligingsteam kan helpen bij hun dagelijkse taken.

De evaluatieervaring van Microsoft Defender voor [Office 365](defender-for-office-365.md) is ontworpen om de complexiteit van de apparaat- en omgevingsconfiguratie te elimineren, zodat u zich kunt concentreren op het evalueren van de mogelijkheden van Microsoft Defender voor Office 365. Met de evaluatiemodus kunnen alle berichten die naar Exchange Online-postvakken worden verzonden, worden geëvalueerd zonder MX-records naar Microsoft te wijzen. De functie is alleen van toepassing op e-mailbeveiliging en niet op Office-clients zoals Word, SharePoint of Teams.

Als u nog geen licentie hebt die Microsoft Defender voor Office 365 ondersteunt, kunt u een gratis evaluatie van [30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) dagen starten en de mogelijkheden testen in het Office 365 Security & Compliance center ( https://protection.office.com/homepage) . U zult genieten van de snelle set-up en u kunt deze eenvoudig uitschakelen indien nodig.

## <a name="how-the-evaluation-works"></a>De manier waarop de evaluatie werkt

Defender voor Office 365 maakt in de evaluatiemodus Defender voor Office 365-e-mailbeleid waarin vonnissen, zoals malware, worden logboeken, maar die geen actie ondernemen op berichten. U bent niet verplicht uw MX-recordconfiguratie te wijzigen.

In de evaluatiemodus [worden namens](safe-attachments.md)u [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) veilige bijlagen, veilige [koppelingen](safe-links.md)en op postvakintelligentie gebaseerd imitatiebeleid ingesteld. Alle Defender voor Office 365-beleidsregels worden gemaakt in de niet-afdwingingsmodus op de achtergrond en zijn niet zichtbaar voor u.

Als onderdeel van de installatie configureert de evaluatiemodus ook [Verbeterde filtering voor verbindingslijnen.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) De filternauwkeurigheid wordt verbeterd door ip-adres- en afzendergegevens te behouden, die anders verloren gaan wanneer e-mail door een e-mailbeveiligingsgateway (ESG) loopt voor Defender voor Office 365. Verbeterde filtering voor connectors verbetert ook de filternauwkeurigheid voor uw bestaande EOP-beleid (Exchange Online Protection) tegen spam en anti-phishing.

Het ingeschakelde verbeterde filteren voor connectors verbetert de filternauwkeurigheid, maar kan de bezorging van bepaalde berichten wijzigen als u een ESG hebt voor Defender voor Office 365 en op dit moment EOP-filtering niet overbrugt. Het effect is beperkt tot EOP-beleid. MDO-beleidsregels die zijn ingesteld als onderdeel van de evaluatie, worden gemaakt in de modus niet-afdwingen. Als u de potentiële productie-impact wilt minimaliseren, kunt u alle EOP-filtering omzeilen door een transportregel te maken om het betrouwbaarheidsniveau voor spam (SCL) in te stellen op -1. Zie [De EAC gebruiken om een e-mailstroomregel te maken die](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)de SCL van een bericht in stelt voor meer   informatie.

Wanneer de evaluatiemodus is ingesteld, wordt er dagelijks een rapport bijgewerkt met maximaal 90 dagen gegevens over de berichten die zouden zijn geblokkeerd als het beleid werd geïmplementeerd (bijvoorbeeld verwijderen, verzenden naar ongewenste e-mail, quarantaine). Rapporten worden gegenereerd voor alle Detecties van Defender voor Office 365 en EOP. Ze worden samengevoegd per detectietechnologie (bijvoorbeeld imitatie) en kunnen worden gefilterd op tijdbereik. Daarnaast kunnen berichtenrapporten op aanvraag worden gemaakt om aangepaste draaiingen te maken of om deep dive-berichten te maken met Threat Explorer.

Met de vereenvoudigde set-upervaring kunt u zich richten op:

- De evaluatie uitvoeren
- Een gedetailleerd rapport krijgen
- Het rapport analyseren voor actie
- Het evaluatieresultaat presenteren

## <a name="before-you-begin"></a>Voordat u begint

### <a name="licensing"></a>Licenties

Als u toegang wilt krijgen tot de evaluatie, moet u voldoen aan de licentievereisten. Een van de volgende licenties werkt:

- Abonnement 1 voor Microsoft Defender voor Office 365
- Abonnement 2 voor Microsoft Defender voor Office 365
- Microsoft 365 E5, Microsoft 365 E5-beveiliging
- Office 365 E5

Als u geen van deze licenties hebt, moet u een proeflicentie verkrijgen.

#### <a name="trial"></a>Proefversie

Als u een proeflicentie wilt verkrijgen voor Microsoft Defender voor Office 365, moet u de rol **factureringsbeheerder** of **globale beheerder hebben.** Vraag machtiging aan van iemand met de rol globale beheerder. [Meer informatie over abonnementen en licenties](../../commerce/licenses/subscriptions-and-licenses.md)

Zodra u de juiste rol hebt, is het aanbevolen pad om een proeflicentie te verkrijgen voor Microsoft Defender voor Office 365 (Abonnement 2) in het Microsoft 365-beheercentrum door naar Facturering > Services kopen te gaan. De proefversie bevat een gratis proefversie van 30 dagen voor 25 licenties. [Een proefabonnement voor Microsoft Defender voor Office 365 (Abonnement 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)krijgen.

U hebt een venster van 30 dagen met de evaluatie om geavanceerde bedreigingen te controleren en te rapporteren. U hebt ook de optie om een betaald abonnement te kopen als u de volledige Defender voor Office 365-mogelijkheden wilt hebben.

### <a name="roles"></a>Rollen

**Exchange Online-rollen zijn vereist voor** het instellen van Defender voor Office 365 in de evaluatiemodus. Het toewijzen van een microsoft 365-compliance- of beveiligingsbeheerderrol werkt niet.

- [Meer informatie over machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo)
- [Meer informatie over het toewijzen van beheerdersrollen](../../admin/add-users/assign-admin-roles.md)

De volgende rollen zijn nodig:

|Taak|Rol (in Exchange Online)|
|---|---|
|Krijg een gratis proefversie of koop Microsoft Defender voor Office 365 (Abonnement 2)|Rol van factureringsbeheerder OF globale beheerder|
|Evaluatiebeleid maken|Rol externe en geaccepteerde domeinen; Rol van beveiligingsbeheerder|
|Evaluatiebeleid bewerken|Rol externe en geaccepteerde domeinen; Rol van beveiligingsbeheerder|
|Evaluatiebeleid verwijderen|Rol externe en geaccepteerde domeinen; Rol van beveiligingsbeheerder |
|Evaluatierapport weergeven|Rol beveiligingsbeheerder OF beveiligingslezerrol|
|

### <a name="enhanced-filtering"></a>Verbeterde filtering

Uw Exchange Online Protection-beleid, zoals bulksgewijs en spambeveiliging, blijft hetzelfde. De evaluatie schakelt echter verbeterde filtering voor verbindingslijnen in, wat van invloed kan zijn op uw e-mailstroom en Exchange Online Protection-beleid, tenzij dit wordt overgeslagen.

Met verbeterde filtering voor verbindingslijnen kunnen tenants bescherming tegen spoofing gebruiken. Anti-spoofing wordt niet ondersteund als u een e-mailbeveiligingsgateway (ESG) gebruikt zonder verbeterde filtering voor verbindingslijnen in teschakelen.

### <a name="urls"></a>URL's

URL's worden tijdens de e-mailstroom tot ontploffing gebracht. Als u niet wilt dat specifieke URL's worden gedetoneerd, beheert u de lijst met toegestane URL's op de juiste manier. Zie [De lijst Tenant toestaan/blokkeren beheren](tenant-allow-block-list.md) voor meer informatie.

URL-koppelingen in de e-mailberichten worden niet terugloop, om de impact van de klant te beperken.

### <a name="email-routing"></a>E-mailroutering

Bereid de bijbehorende details voor die u nodig hebt om in te stellen hoe uw e-mail momenteel wordt gerouteerd, inclusief de naam van de inkomende verbindingslijn die uw e-mail routeert. Als u alleen Exchange Online Protection gebruikt, hebt u geen verbindingslijn.  [Meer informatie over e-mailstroom en e-mailroutering](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Ondersteunde e-mailrouteringsscenario's zijn:

- **Externe partner en/of on-premises serviceprovider:** De inkomende connector die u wilt evalueren, maakt gebruik van een externe provider en/of u gebruikt een oplossing voor on-premises e-mailbeveiliging.
- **Alleen Microsoft Exchange Online Protection:** De tenant die u wilt evalueren, gebruikt Office 365 voor e-mailbeveiliging en de MX-record (Mail Exchange) wijst naar Microsoft.

### <a name="email-security-gateway"></a>E-mailbeveiligingsgateway

Als u een externe e-mailbeveiligingsgateway (ESG) gebruikt, moet u de naam van de provider weten. Als u een on-premises of niet-ondersteunde ESG-leverancier gebruikt, moet u het openbare IP-adres(es) voor de apparaten kennen.

Ondersteunde partners van derden zijn:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Scoping

U kunt de evaluatie naar een binnenkomende verbindingslijn toveren. Als er geen connector is geconfigureerd, kunnen beheerders met het evaluatiebereik gegevens verzamelen van gebruikers in uw tenant om Defender voor Office 365 te evalueren.

## <a name="get-started-with-the-evaluation"></a>Aan de slag met de evaluatie

Zoek de evaluatieset-upkaart van Microsoft Defender voor Office 365 in het Office 365-beveiligings- & Compliancecentrum https://protection.office.com/homepage) (vanaf drie toegangspunten:

- Bedreigingsbeheer > Dashboard
- Bedreigingsbeheer > beleid
- Rapporten > Dashboard

## <a name="setting-up-the-evaluation"></a>De evaluatie instellen

Wanneer u de set-upstroom voor de evaluatie start, krijgt u twee routeringsopties. Afhankelijk van de e-mailrouterings- en evaluatiebehoeften van uw organisatie, kunt u selecteren of u een externe en/of on-premises serviceprovider of alleen Microsoft Exchange Online gebruikt.

- Als u een externe partner en/of on-premises serviceprovider gebruikt, moet u de naam van de leverancier selecteren in de vervolgkeuzelijst. Geef de andere connectorgerelateerde details op.

- Selecteer Microsoft Exchange Online als de MX-record naar Microsoft wijst en u een Exchange Online-postvak hebt.

Controleer uw instellingen en bewerk deze indien nodig. Selecteer vervolgens **Evaluatie maken.** U ontvangt een bevestigingsbericht om aan te geven dat de set-up is voltooid.

Uw evaluatierapport van Microsoft Defender voor Office 365 wordt eenmaal per dag gegenereerd. Het kan tot 24 uur duren voordat de gegevens zijn ingevuld.

### <a name="exchange-rules-optional"></a>Exchange-regels (optioneel)

Als u een bestaande gateway hebt, wordt in de evaluatiemodus verbeterde filtering voor verbindingslijnen geactiveerd. Dit verbetert de nauwkeurigheid van het filteren door het IP-adres van de binnenkomende afzender te wijzigen. Dit kan de filteruitspraken wijzigen en als u Exchange Online Protection niet overbrugt, kan dit de bezorgbaarheid van bepaalde berichten wijzigen. In dit geval wilt u het filteren mogelijk tijdelijk omzeilen om de impact te analyseren. Als u wilt omzeilen, gaat u naar het Exchange-beheercentrum en maakt u een beleid van SCL -1 (als u er nog geen hebt). Zie Regels voor e-mailstroom (transportregels) in Exchange Online voor meer informatie over de regelonderdelen en hoe ze werken.

## <a name="evaluate-capabilities"></a>Mogelijkheden evalueren

Nadat het evaluatierapport is gegenereerd, bekijkt u hoeveel geavanceerde bedreigingskoppelingen, geavanceerde bedreigingsbijlagen en potentiële imitaties zijn geïdentificeerd in de werkruimten voor e-mails en samenwerking in uw organisatie.

Nadat de proefversie is verlopen, kunt u het rapport 90 dagen blijven openen. Er wordt echter geen informatie meer verzameld. Als u Microsoft Defender voor Office 365 wilt blijven gebruiken nadat uw proefabonnement is verlopen, moet u een betaald abonnement kopen voor Microsoft Defender voor [Office 365 (abonnement 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

U kunt op elk moment naar **Instellingen** gaan om uw routering bij te werken of de evaluatie uit te schakelen. U moet echter opnieuw hetzelfde in te stellen proces doorlopen als u besluit om door te gaan met de evaluatie nadat u deze hebt uitgeschakeld.

## <a name="provide-feedback"></a>Feedback geven

Met uw feedback kunnen we uw omgeving beter beschermen tegen geavanceerde aanvallen. Deel uw ervaring en indrukken van productmogelijkheden en evaluatieresultaten.

Selecteer **Feedback geven** om ons te laten weten wat u denkt.