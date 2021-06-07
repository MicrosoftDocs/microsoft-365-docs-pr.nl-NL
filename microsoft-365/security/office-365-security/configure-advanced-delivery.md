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
description: Beheerders kunnen leren hoe ze het beleid voor geavanceerde bezorging in Exchange Online Protection (EOP) kunnen gebruiken om berichten te identificeren die niet moeten worden gefilterd in specifieke ondersteunde scenario's (phishingsimulaties van derden en berichten die worden bezorgd in postvakken van beveiligingsbewerkingen (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a9c1c6f7635b87e25adcb121db79f67d4ec1988f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788992"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>De bezorging van phishingsimulaties van derden configureren voor gebruikers en ongefilterde berichten in SecOps-postvakken

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> De functie die in dit artikel wordt beschreven, is in Preview, is niet voor iedereen beschikbaar en kan worden gewijzigd.

Als u uw organisatie standaard veilig wilt [houden,](secure-by-default.md)staat Exchange Online Protection (EOP) geen veilige lijsten of filtering bypass toe voor berichten die zijn geïdentificeerd als malware of phishing met een hoog vertrouwen. Er zijn echter specifieke scenario's waarvoor niet-gefilterde berichten moeten worden bezorgd. Bijvoorbeeld:

- **Phishingsimulaties** van derden: Gesimuleerde aanvallen kunnen u helpen om kwetsbare gebruikers te identificeren voordat een echte aanval van invloed is op uw organisatie.
- **Postvakken voor beveiligingsbewerkingen (SecOps)**: Speciale postvakken die door beveiligingsteams worden gebruikt om ongefilterde berichten te verzamelen en te analyseren (zowel goed als slecht).

U gebruikt het _geavanceerde bezorgingsbeleid_ in Microsoft 365 om te voorkomen dat deze berichten _in_ deze specifieke scenario's worden gefilterd. <sup>\*</sup> Het geavanceerde bezorgingsbeleid zorgt ervoor dat berichten in deze scenario's de volgende resultaten bereiken:

- Filters in EOP en Microsoft Defender voor Office 365 actie ondernemen op deze berichten.<sup>\*</sup>
- [Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) voor spam en phishing onderneemt geen actie op deze berichten.<sup>\*</sup>
- [Standaardsysteemwaarschuwingen](alerts.md) worden niet geactiveerd voor deze scenario's.
- [Air en clustering in Defender voor Office 365](office-365-air.md) negeert deze berichten.
- Specifiek voor phishingsimulaties van derden:
  - [Beheerdersinzendingen genereren](admin-submission.md) een automatisch antwoord met de melding dat het bericht deel uitmaakt van een phishingsimulatiecampagne en geen echte bedreiging is. Waarschuwingen en AIR worden niet geactiveerd.
  - [Safe Koppelingen in Defender voor Office 365](safe-links.md) worden de specifiek geïdentificeerde URL's in deze berichten niet geblokkeerd of tot ontploffing gebracht.
  - [Safe bijlagen in Defender voor Office 365](safe-attachments.md) worden bijlagen in deze berichten niet tot ontploffing brengen.

<sup>\*</sup> U kunt malwarefilters of ZAP voor malware niet omzeilen.

Berichten die worden geïdentificeerd door het geavanceerde bezorgingsbeleid zijn geen beveiligingsrisico's, dus de berichten worden gemarkeerd als systeem overschrijven. Beheerders kunnen deze systeem overschrijven en analyseren in de volgende ervaringen:

- [Threat Explorer/Real-time detecties in Defender voor Office 365 plan 2](threat-explorer.md)
- De [pagina E-mailentiteit in Threat Explorer/Realtime detecties](mdo-email-entity-page.md)
- Het [rapport Status van bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
- [Advanced hunting in Microsoft Defender for Endpoint](../defender-endpoint/advanced-hunting-overview.md)
- [Campagneweergaven](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligingscentrum in <https://security.microsoft.com>. Als u rechtstreeks naar de pagina **Geavanceerde bezorging wilt** gaan, opent u <https://security.microsoft.com/advanceddelivery> .

- U moet machtigingen hebben toegewezen voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u geconfigureerde instellingen wilt maken, wijzigen of verwijderen in het  geavanceerde bezorgingsbeleid, moet u lid  zijn van de rollengroep Beveiligingsbeheerder in het **beveiligingscentrum** en lid zijn van de rollengroep Organisatiebeheer in **Exchange Online.**  
  - Voor alleen-lezen toegang tot het geavanceerde bezorgingsbeleid moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie Machtigingen [in het](permissions-microsoft-365-security-center.md) Microsoft 365 beveiligingscentrum en [Machtigingen in](/exchange/permissions-exo/permissions-exo)Exchange Online.

  > [!NOTE]
  > Gebruikers toevoegen aan de bijbehorende Azure Active Directory geeft gebruikers de vereiste machtigingen in het beveiligingscentrum en _machtigingen_ voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="use-the-security-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Het beveiligingscentrum gebruiken om SecOps-postvakken te configureren in het beleid voor geavanceerde bezorging

1. Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & regels \>  \> **Bedreigingsbeleidsregels** \>  sectie \> **Geavanceerde bezorging**.

2. Controleer op **de pagina** Geavanceerde bezorging of het **tabblad SecOps-postvak** is geselecteerd en ga vervolgens op een van de volgende stappen te werk:
   - Klik ![ op Pictogram Bewerken ](../../media/m365-cc-sc-edit-icon.png) **Bewerken.**
   - Als er geen geconfigureerde phishingsimulaties zijn, klikt u op **Toevoegen.**

3. Voer in **het flyout SecOps-postvakken** bewerken dat wordt geopend een bestaand Exchange Online-postvak in dat u wilt aanwijzen als SecOps-postvak door een van de volgende stappen uit te voeren:
   - Klik in het vak, laat de lijst met postvakken oplossen en selecteer het postvak.
   - Klik in het vak om een id voor het postvak te typen (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) en selecteer het postvak (weergavenaam) in de resultaten.

     Herhaal deze stap zo vaak als nodig is. Distributiegroepen zijn niet toegestaan.

     Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.

4. Klik op **Opslaan** wanneer u gereed bent.

De secops-postvakinzendingen die u hebt geconfigureerd, worden weergegeven op het **tabblad SecOps-postvak.** Als u wijzigingen wilt aanbrengen, klikt ![ u op Het tabblad ](../../media/m365-cc-sc-edit-icon.png) **bewerken** op Pictogram Bewerken.

## <a name="use-the-security-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Gebruik het beveiligingscentrum om phishingsimulaties van derden te configureren in het beleid voor geavanceerde bezorging

1. Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & regels \>  \> **Bedreigingsbeleidsregels** \>  sectie \> **Geavanceerde bezorging**.

2. Selecteer op **de pagina** Geavanceerde bezorging het **tabblad Phishingsimulatie** en ga vervolgens op een van de volgende stappen te werk:
   - Klik ![ op Pictogram Bewerken ](../../media/m365-cc-sc-edit-icon.png) **Bewerken.**
   - Als er geen geconfigureerde phishingsimulaties zijn, klikt u op **Toevoegen.**

3. Configureer de volgende instellingen in het flyout **phishingsimulatie** van derden bewerken dat wordt geopend:

   - **Domein** verzenden: Vouw deze instelling uit en voer ten minste één e-mailadresdomein in (bijvoorbeeld contoso.com) door in het vak te klikken, een waarde in te voeren en vervolgens op Enter te drukken of de waarde te selecteren die onder het vak wordt weergegeven. Herhaal deze stap zo vaak als nodig is. U kunt maximaal tien items toevoegen.
   - **IP verzenden:** Vouw deze instelling uit en voer ten minste één geldig IPv4-adres in door in het vak te klikken, een waarde in te voeren en vervolgens op Enter te drukken of de waarde te selecteren die onder het vak wordt weergegeven. Herhaal deze stap zo vaak als nodig is. U kunt maximaal tien items toevoegen. Geldige waarden zijn:
     - Enkel IP: bijvoorbeeld 192.168.1.1.
     - IP-bereik: bijvoorbeeld 192.168.0.1-192.168.0.254.
     - CIDR IP: Bijvoorbeeld 192.168.0.1/25.
   - **Url's** voor simulaties om dit mogelijk te maken: Vouw deze instelling uit en voer desgewenst specifieke URL's in die deel uitmaken van uw phishingsimulatiecampagne die niet mogen worden geblokkeerd of gedetoneerd door in het vak te klikken, een waarde in te voeren en vervolgens op Enter te drukken of de waarde te selecteren die onder het vak wordt weergegeven. U kunt maximaal tien items toevoegen.

   Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.

4. Wanneer u klaar bent, gaat u op een van de volgende stappen te werk:
   - **Eerste keer:** Klik **op Toevoegen** en klik vervolgens op **Sluiten.**
   - **Bestaand bewerken:** Klik **op Opslaan** en klik vervolgens op **Sluiten.**

De phishingsimulatiegegevens van derden die u hebt geconfigureerd, worden weergegeven op het **tabblad Phishingsimulatie.** Als u wijzigingen wilt aanbrengen, klikt ![ u op Het tabblad ](../../media/m365-cc-sc-edit-icon.png) **bewerken** op Pictogram Bewerken.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Extra scenario's waarvoor filteren moet worden omzeild

Naast de twee scenario's waar het geavanceerde bezorgingsbeleid u bij kan helpen, zijn er andere scenario's waarvoor het filteren mogelijk moet worden overgeslagen:

- **Filters van derden:** Als de MX-record  van uw domein niet naar Office 365 (berichten worden eerst ergens anders gerouteerd), is beveiliging standaard niet [](secure-by-default.md) *beschikbaar.*

  Gebruik e-mailstroomregels (ook wel transportregels genoemd) om Microsoft-filtering te omzeilen voor berichten die al zijn geëvalueerd door filtering van derden. Zie E-mailstroomregels gebruiken om de SCL in berichten [in te stellen voor meer informatie.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)

- **False positives under review**: U wilt mogelijk bepaalde berichten die nog steeds door Microsoft worden geanalyseerd [via](admin-submission.md) beheerdersinzendingen tijdelijk toestaan om bekende goede berichten te melden die ten onrechte als slecht worden gemarkeerd voor Microsoft (false positives). Net als bij alle **** overschrijvingen wordt ten zeerste aanbevolen dat deze vergoedingen tijdelijk zijn.
