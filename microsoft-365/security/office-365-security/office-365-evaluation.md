---
title: Evalueer Microsoft Defender for Office 365
description: Met de evaluatieversie van 365 kunt u in de evaluatiemodus voor Office 365 e-mail beleidsregels maken voor Verdicts, zoals malware, maar geen actie ondernemen op berichten.
keywords: Evalueer Office 365, Microsoft Defender for Office 365, Office 365-evaluatie, Probeer Office 365, Microsoft Defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 12b6499822f8ed97ace8468054f219361d925332
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562988"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Evalueer Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

>[!IMPORTANT]
>Evalueer Microsoft Defender for Office 365 zal binnenkort in de openbare preview-versie worden weergegeven zonder een serviceovereenkomst. Het is mogelijk dat bepaalde functies niet worden ondersteund of mogelijk een beperkte functionaliteit hebben.

U kunt een uitgebreide beoordeling van de veiligheid van het product bieden om u op de hoogte te stellen van upgrades en aankopen. Het is handig om de mogelijkheden van het beveiligings product uit te proberen om te beoordelen hoe dit uw team van beveiligingsactiviteiten kan helpen bij hun dagelijkse taken.

Met de evaluatieversie van [Microsoft Defender voor Office 365](office-365-atp.md) kunt u de complexe functies van de apparatuur en de omgevings configuratie elimineren, zodat u zich kunt concentreren op het evalueren van de mogelijkheden van de beveiligingsoplossing. Dit geldt alleen voor e-mail beveiliging en niet voor SharePoint, Office-clients of teams.

Als u nog geen licentie hebt die ondersteuning biedt voor Microsoft Defender voor Office 365, kunt u een gratis proefversie van [30 dagen](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) starten en de functies testen in de beveiligings & van Office 365 https://protection.office.com/homepage) . U kunt snel aan de slag met de set en u kunt deze zo nodig eenvoudig uitschakelen.

## <a name="how-the-evaluation-works"></a>De werking van de evaluatie

Met de evaluatieversie van 365 kunt u in de evaluatiemodus voor Office 365 e-mail beleidsregels maken voor Verdicts, zoals malware, maar geen actie ondernemen op berichten. U bent niet verplicht om uw MX-record configuratie te wijzigen.

Met de evaluatiemodus, [veilige bijlagen](atp-safe-attachments.md), [veilige koppelingen](atp-safe-links.md)en [beleid voor anti-phishing](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) , wordt namens u ingesteld. Alle beleidsregels voor Defender voor Office 365 worden met de niet-afdwingbare modus gemaakt en zijn niet zichtbaar voor u.

Als onderdeel van de instelling, configureert de evaluatiemodus ook [uitgebreid filteren op connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors). De nauwkeurigheid van het filteren van IP-adressen en gegevens over de afzender wordt op een andere manier verduurzaamd wanneer e-mail wordt doorgestuurd via een ESG (MailSecurity gateway) vóór de app voor Office 365. Hierdoor wordt het filteren van de filters nauwkeuriger voor uw EOP-antispam-en Antispambeleid voor Exchange Online Protection ook verbeterd.

Als u de potentiële productie-impact op sommige niet-ondersteunde scenario's wilt beperken, kunt u alle filters filteren negeren door een transportregel te maken voor het instellen van het spam betrouwbaarheidsniveau (SCL) op-1. Zie voor meer informatie [een e-mail stroom regel maken waarmee de SCL van een bericht wordt ingesteld](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   voor informatie.

Wanneer de evaluatiemodus is geconfigureerd, hebt u dagelijks een rapport bijgewerkt met een maximum van 90 dagen van de gegevens die zijn geblokkeerd, omdat het beleid is gemaakt en geïmplementeerd (bijvoorbeeld verwijderen, verzenden naar ongewenste e-mail, Quarantine). Er worden rapporten gegenereerd voor alle EOP-en detectie punten van de Defender voor Office 365. De persoon wordt samengevoegd per detectietechnologie (bijvoorbeeld imitatie) en kan worden gefilterd op tijdsbereik. Daarnaast kunnen berichten rapporten op aanvraag worden gemaakt om aangepaste draaiingen te maken of berichten van een grondige uitduiking te maken met behulp van de bedreigings Verkenner.

Met een eenvoudige instelling kunt u zich richten op:

- De evaluatie uitvoeren
- Een gedetailleerd rapport verkrijgen
- Het rapport analyseren voor actie
- Het resultaat van de evaluatie presenteren

## <a name="before-you-begin"></a>Voordat u begint

### <a name="licensing"></a>Licenties

Voor toegang tot de evaluatie moet u voldoen aan de licentievereisten. De volgende licenties werken wel:

- Abonnement 1 voor Microsoft Defender voor Office 365
- Microsoft Defender voor Office 365, abonnement 2
- Microsoft 365 E5, Microsoft 365 E5-beveiliging
- Office 365 E5

Als u niet een van deze licenties hebt, moet u een proeflicentie aanvragen.

#### <a name="trial"></a>Lange

Als u een proeflicentie voor Microsoft Defender voor Office 365 wilt verkrijgen, moet u beschikken over de rol van **factureringsbeheerder** of **globale beheerder**. Vraagt om toestemming van iemand met de rol van globale beheerder. [Meer informatie over abonnementen en licenties](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

Wanneer u de juiste rol hebt, is het aanbevolen pad om een proeflicentie voor Microsoft Defender for Office 365 (abonnement 2) te verkrijgen in het Microsoft 365-Beheercentrum via facturering > Services aanschaffen. De proefperiode omvat een gratis proefversie van 30 dagen voor 25 licenties. U [ontvangt een proefabonnement voor Microsoft Defender for Office 365 (abonnement 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA). 

U hebt een venster van dertig dagen met de evaluatie voor het bewaken van en rapporteren over geavanceerde bedreigingen. U kunt ook een betaald abonnement kopen als u de volledige functionaliteit van de Defender voor Office 365 wilt gebruiken.

### <a name="roles"></a>Vervullen

Exchange Online-rollen zijn vereist voor het instellen van Defender voor Office 365 in de evaluatiemodus. U hebt de volgende rollen nodig:

|Taak | Rol |
|-----| -----|
| Maak een gratis proefversie of koop Microsoft Defender for Office 365 (abonnement 2)| Rol van factureringsbeheerder of globale beheerder|
| Evaluatie beleid maken| De rol van extern en geaccepteerde domeinen; Rollen van beveiligingsbeheerders|
| Evaluatie beleid bewerken | De rol van extern en geaccepteerde domeinen; Rollen van beveiligingsbeheerders |
| Evaluatie beleid verwijderen | De rol van extern en geaccepteerde domeinen; Rollen van beveiligingsbeheerders |
|Evaluatieverslag weergeven | Rol van beveiligingsbeheerder of beveiligings lezer|

### <a name="enhanced-filtering"></a>Uitgebreid filteren

Uw beleid voor Exchange Online beveiliging, zoals beveiliging tegen bulk en spam, blijft ongewijzigd. Berichtbezorging blijft ook ongewijzigd. Met de evaluatie wordt echter uitgebreid filteren van connectors ingeschakeld, wat van invloed is op uw e-mail stroom en Exchange Online Protection-beleid, tenzij ze worden overgeslagen.

Met een betere filtering voor Connectors kunnen tenants beveiliging tegen spoofing gebruiken. Anti-spoofing wordt niet ondersteund als u werkt met een e-mail beveiligingsgateway (ESG) zonder dat u een verbeterde filtering voor connectors hoeft in te schakelen.

### <a name="urls"></a>URLs

Url's worden tijdens de e-mail stroom weergegeven. Als u bepaalde Url's niet wilt weergeven, beheert u de lijst met toegestane Url's op de juiste manier. Zie [Url's beheren in de lijst Tenant toestaan/blokkeren](tenant-allow-block-list.md) voor meer informatie.

URL-koppelingen in de berichttekst van een e-mailbericht kunnen niet teruglopen om de gevolgen van klanten te beperken.

### <a name="email-routing"></a>E-mail routering

U moet de bijbehorende Details voorbereiden die u moet instellen voor de manier waarop uw e-mailberichten momenteel worden gerouteerd, waaronder de naam van de inkomende connector waarmee uw e-mail wordt rondgestuurd. Als u alleen Exchange Online Protection gebruikt, hebt u geen connector.  [Meer informatie over e-mail stroom en e-mail routering](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Ondersteunde e-mail routeringsscenario's zijn:

- **Partner van derden en/of on-premises service provider**: de binnenkomende verbindingslijn die u wilt evalueren, maakt gebruik van een externe provider en/of u gebruikt een oplossing voor e-mail beveiliging.  
- **Alleen Microsoft Exchange Online Protection**: de Tenant die u wilt evalueren, maakt gebruik van Office 365 voor e-mail beveiliging en de MX-record (mail exchanger) van Microsoft.

### <a name="email-security-gateway"></a>Beveiligingsgateway voor e-mail

Als u een e-mail beveiligingsgateway voor derden gebruikt (ESG), moet u de naam van de provider weten. Als u een on-premises of niet-ondersteunde leverancier van ESG gebruikt, moet u weten wat de openbare IP-adressen voor de apparaten zijn.

Ondersteunde partners van derden omvatten:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Volgen

U kunt de evaluatie in een inkomende connector bereiken. Als er geen connector is geconfigureerd, kunnen beheerders met het evaluatie bereik gegevens van een willekeurige gebruiker in de Tenant verzamelen om de functies van Defender voor Office 365 te evalueren.

## <a name="get-started-with-the-evaluation"></a>Aan de slag met de evaluatie

Zoek de installatie kaart voor Microsoft Defender for Office 365 op de proefversie van Office 365 & compliance ( https://protection.office.com/homepage) van drie toegangspunten).

- Threat Management > dashboard
- Beleid voor risicobeheer >
- Rapporten > dashboard

## <a name="setting-up-the-evaluation"></a>De evaluatie instellen

Wanneer u de ingestelde stroom instelt voor de evaluatie, krijgt u twee routeringsopties. Afhankelijk van de instellingen voor e-mail routering van uw organisatie en de behoeften van uw organisatie, kunt u aangeven of u een externe provider of een on-premises service provider of alleen Microsoft Exchange Online gebruikt.

- Als u een partner van derden en/of on-premises service provider gebruikt, moet u de naam van de leverancier selecteren in het vervolgkeuzemenu. Voer de andere informatie over de connector in.

- Selecteer Microsoft Exchange Online als de MX-record verwijst naar Microsoft en u een postvak van Exchange Online hebt.

Controleer de instellingen en bewerk deze zo nodig. Selecteer vervolgens **evaluatie maken**. U ontvangt een bevestigingsbericht om aan te geven dat uw instellingen zijn voltooid.

Uw evaluatierapport van Microsoft Defender voor Office 365 wordt één keer per dag gegenereerd. Het kan tot 24 uur duren voordat de gegevens zijn ingevuld.

### <a name="exchange-rules-optional"></a>Exchange-regels (optioneel)

Als u een bestaande gateway hebt, wilt u deze mogelijk niet meer filteren, omdat het IP-adres van de binnenkomende afzender wordt geactiveerd. Als u wilt negeren, gaat u naar het Exchange-Beheercentrum en maakt u een beleid van SCL-1 (als u dat nog niet hebt gedaan). Zie regels voor e-mail stroom (transportregels) in Exchange Online voor meer informatie over de regel onderdelen en hoe deze werken.

## <a name="evaluate-capabilities"></a>Mogelijkheden evalueren

Wanneer het evaluatierapport is gegenereerd, raadpleegt u het aantal geavanceerde bedreigings koppelingen, geavanceerde bijlagen met bedreigingen en mogelijke oorzaken werden aangegeven in de werkruimten voor e-mailberichten en samenwerking in uw organisatie.  

Wanneer de proefperiode is verlopen, kunt u het rapport nog voor 90 dagen openen. Er is echter geen informatie verzameld. Als u Microsoft Defender voor Office 365 wilt blijven gebruiken nadat uw proefabonnement is verlopen, moet u ervoor zorgen dat u [een betaald abonnement koopt voor Microsoft Defender for Office 365 (abonnement 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

U kunt op elk gewenst moment naar **instellingen** gaan om uw routering bij te werken of de evaluatie uit te schakelen. U moet echter wel hetzelfde proces voor het instellen van het proces doorlopen wanneer u het hebt uitgeschakeld.

## <a name="provide-feedback"></a>Feedback geven

Met uw feedback kunnen we uw omgeving beter beschermen tegen geavanceerde aanvallen. Deel de ervaring en indruk van product mogelijkheden en evaluatieresultaten.

Selecteer **feedback geven** om ons te laten weten wat u ervan vindt.
