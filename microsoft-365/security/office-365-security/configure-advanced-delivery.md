---
title: De bezorging van phishingsimulaties van derden configureren voor gebruikers en ongefilterde berichten in SecOps-postvakken
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Beheerders kunnen leren hoe ze het beleid voor geavanceerde bezorging in Exchange Online Protection (EOP) kunnen gebruiken om berichten te identificeren die niet mogen worden gefilterd in specifieke ondersteunde scenario's (phishingsimulaties van derden en berichten die worden bezorgd in postvakken van beveiligingsbewerkingen (SecOps).
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX
ms.openlocfilehash: 09e07d8406b470fd3dac25944d013b997f2f90c1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760429"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>De bezorging van phishingsimulaties van derden configureren voor gebruikers en ongefilterde berichten in SecOps-postvakken

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> De functie die in dit artikel wordt beschreven, is in Preview, is niet voor iedereen beschikbaar en kan worden gewijzigd.

We willen uw [](secure-by-default.md)organisatie standaard beveiligen, zodat eOP (Exchange Online Protection) geen veilige lijsten toestaat of bypassfilters filtert voor berichten die leiden tot malware of phishing met veel vertrouwen. We herkennen echter dat er specifieke scenario's zijn waarvoor niet-gefilterde berichten moeten worden bezorgd. Bijvoorbeeld:

- **Phishingsimulaties** van derden: Gesimuleerde aanvallen kunnen u helpen om kwetsbare gebruikers te identificeren voordat een echte aanval van invloed is op uw organisatie.
- **Postvakken voor beveiligingsbewerkingen (SecOps)**: Speciale postvakken die door beveiligingsteams worden gebruikt om ongefilterde berichten te verzamelen en te analyseren (zowel goed als slecht).

U gebruikt het _geavanceerde bezorgingsbeleid_ in Microsoft 365 om te voorkomen dat deze berichten _in_ deze specifieke scenario's worden gefilterd. <sup>\*</sup> Het geavanceerde bezorgingsbeleid zorgt ervoor dat berichten in deze scenario's niet worden gefilterd:

- Filters in EOP en Microsoft Defender voor Office 365 nemen geen actie op deze berichten.<sup>\*</sup>
- [Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) voor spam en phishing onderneemt geen actie op deze berichten.<sup>\*</sup>
- [Standaardsysteemwaarschuwingen](alerts.md) worden niet geactiveerd voor deze scenario's.
- [Air en clustering in Defender voor Office 365](office-365-air.md) negeren deze berichten.
- Specifiek voor phishingsimulaties van derden:
  - [Beheerdersinzendingen genereren](admin-submission.md) een automatisch antwoord waarin wordt aangegeven dat het bericht deel uitmaakt van een phishingsimulatiecampagne en geen echte bedreiging is. Waarschuwingen en AIR worden niet geactiveerd.
  - [Met veilige koppelingen in Defender voor Office 365](safe-links.md) worden de specifiek geïdentificeerde URL's in deze berichten niet geblokkeerd of tot ontploffing gebracht.
  - [Met veilige bijlagen in Defender voor Office 365](safe-attachments.md) worden bijlagen in deze berichten niet afgebouwd.

<sup>\*</sup> U kunt malwarefilters of ZAP voor malware niet omzeilen.

Berichten die worden geïdentificeerd door het geavanceerde bezorgingsbeleid zijn geen beveiligingsrisico's, dus de berichten worden gemarkeerd als systeem overschrijven. Beheerders kunnen deze systeem overschrijven en analyseren in de volgende ervaringen:

- [Bedreigingsverkenner/realtimedetecties in Defender voor Office 365-abonnement 2](threat-explorer.md)
- De [pagina E-mailentiteit in Threat Explorer/Realtime detecties](mdo-email-entity-page.md)
- Het [rapport Status van bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
- [Advanced hunting in Microsoft Defender for Endpoint](../defender-endpoint/advanced-hunting-overview.md)
- [Campagneweergaven](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Geavanceerde bezorging wilt** gaan, opent u <https://protection.office.com/advanceddelivery> .

- U moet machtigingen hebben toegewezen voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u geconfigureerde instellingen wilt maken, wijzigen of verwijderen in het  geavanceerde bezorgingsbeleid, moet u lid zijn van de  rollengroep Beveiligingsbeheerder in het **beveiligings- & compliancecentrum** en lid zijn van de rollengroep Organisatiebeheer in **Exchange Online.**  
  - Voor alleen-lezen toegang tot het geavanceerde bezorgingsbeleid moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie Machtigingen [in het Beveiligings-](permissions-in-the-security-and-compliance-center.md) & Compliancecentrum en [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo)voor meer informatie.

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Gebruik het Beveiligings- & compliancecentrum om phishingsimulaties van derden te configureren in het geavanceerde bezorgingsbeleid

1. Ga in het & Compliance center naar **Threat management** \> **Policy Advanced** \> **delivery**.

2. Selecteer op **de pagina Geavanceerde** bezorging het tabblad **Phishingsimulatie** en klik vervolgens op **Bewerken.**

3. Configureer de volgende instellingen **in de flyout phishingsimulatie** van derden die wordt geopend:

   - **Domein verzenden:** Er is ten minste één e-mailadresdomein vereist (bijvoorbeeld contoso.com). U kunt maximaal tien items toevoegen.
   - **IP-adres** verzenden: Minimaal één geldig IPv4-adres is vereist. U kunt maximaal tien items toevoegen. Geldige waarden zijn:
     - Enkel IP: bijvoorbeeld 192.168.1.1.
     - IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.
     - CIDR IP: Bijvoorbeeld 192.168.0.1/25.
   - **Url's voor** simulaties om toe te staan: Voer desgewenst specifieke URL's in die deel uitmaken van uw phishingsimulatiecampagne die niet mogen worden geblokkeerd of tot ontploffing mogen worden gebracht. U kunt maximaal tien items toevoegen.

4. Wanneer u klaar bent, klikt u op **Opslaan.**

De phishingsimulatiegegevens van derden die u hebt geconfigureerd, worden weergegeven op het **tabblad Phishingsimulatie.** Als u wijzigingen wilt aanbrengen, klikt **u op Bewerken** op het tabblad.

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Gebruik het Beveiligings- & compliancecentrum om SecOps-postvakken te configureren in het geavanceerde bezorgingsbeleid

1. Ga in het & compliancecentrum naar **Geavanceerde bezorging van bedreigingsbeleidsbeleid.** \>  \> 

2. Selecteer op **de pagina Geavanceerde** bezorging het tabblad **SecOps-postvak** en klik vervolgens op **Bewerken.**

3. Voer in **het flyout SecOps-postvak** dat wordt geopend de e-mailadressen in van bestaande Exchange Online-postvakken die u wilt aanwijzen als SecOps-postvakken. Distributiegroepen zijn niet toegestaan.

4. Klik op **Opslaan** wanneer u gereed bent.

De secops-postvakinzendingen die u hebt geconfigureerd, worden weergegeven op het **tabblad SecOps-postvak.** Als u wijzigingen wilt aanbrengen, klikt **u op Bewerken** op het tabblad.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Extra scenario's waarvoor filteren moet worden omzeild

Naast de twee scenario's waar het geavanceerde bezorgingsbeleid u bij kan helpen, zijn er andere scenario's waarvoor het filteren mogelijk moet worden overgeslagen:

- **Filters van derden:** Als de MX-record van het domein niet naar Office 365 wijst (berichten worden eerst ergens anders gerouteerd), [](secure-by-default.md) is beveiliging standaard niet beschikbaar.

  Als u microsoft-filtering wilt omzeilen voor berichten die al zijn geëvalueerd door filtering van derden, gebruikt u regels voor e-mailstroom (ook wel transportregels genoemd), zie E-mailstroomregels gebruiken om de SCL in berichten [in te stellen.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- **False positives under review**: U wilt mogelijk bepaalde berichten die nog steeds door Microsoft worden geanalyseerd [via](admin-submission.md) beheerdersinzendingen tijdelijk toestaan om bekende goede berichten te melden die ten onrechte als slecht worden gemarkeerd voor Microsoft (false positives). Net als bij alle overschrijvingen wordt ten zeerste aanbevolen dat deze vergoedingen tijdelijk zijn.
