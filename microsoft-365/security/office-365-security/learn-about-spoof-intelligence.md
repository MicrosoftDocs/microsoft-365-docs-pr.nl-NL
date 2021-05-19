---
title: Inzicht in spoofinformatie
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over het inzicht in spoof intelligence in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 37c5bcb6f2c15c3814fafa198f2905e23b12ba01
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538745"
---
# <a name="spoof-intelligence-insight-in-eop"></a>Inzicht in spoof intelligence in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> De functies die in dit artikel worden beschreven, zijn in Preview, kunnen worden gewijzigd en zijn niet beschikbaar in alle organisaties. Als uw organisatie niet beschikt over de functies die in dit artikel worden beschreven, bekijkt u de oudere spoofbeheerervaring bij Vervalste afzenders beheren met behulp van het spoof intelligence-beleid en het inzicht in spoof [intelligence in EOP.](walkthrough-spoof-intelligence-insight.md)

In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection -organisaties zonder Exchange Online-postvakken, worden binnenkomende e-mailberichten automatisch beschermd tegen spoofing. EOP gebruikt **spoof intelligence** als onderdeel van de algehele verdediging van uw organisatie tegen phishing. Zie Bescherming tegen spoofing in [EOP voor meer informatie.](anti-spoofing-protection.md)

Wanneer een afzender een e-mailadres vervalst, lijkt deze een gebruiker te zijn in een van de domeinen van uw organisatie of een gebruiker in een extern domein die e-mail naar uw organisatie verzendt. Aanvallers die afzenders spoofen om spam of phishing-e-mail te verzenden, moeten worden geblokkeerd. Maar er zijn scenario's waarin legitieme afzenders spoofing gebruiken. Bijvoorbeeld:

- Legitieme scenario's voor het vervalsen van interne domeinen:
  - Afzenders van derden gebruiken uw domein om bulkmail naar uw eigen werknemers te verzenden voor bedrijfspeilingen.
  - Een extern bedrijf genereert en verzendt namens u reclame- of productupdates.
  - Een assistent moet regelmatig e-mail verzenden voor een andere persoon binnen uw organisatie.
  - Met een interne toepassing worden e-mailmeldingen verzonden.

- Legitieme scenario's voor spoofing van externe domeinen:
  - De afzender staat op een adressenlijst (ook wel een discussielijst genoemd) en de adressenlijst geeft e-mail door van de oorspronkelijke afzender naar alle deelnemers op de adressenlijst.
  - Een extern bedrijf verzendt e-mail namens een ander bedrijf (bijvoorbeeld een geautomatiseerd rapport of een software-as-a-servicebedrijf).

U kunt het inzicht in spoof intelligence **in** het Beveiligings- & Compliancecentrum gebruiken om snel vervalste afzenders te identificeren die u legitiem niet-genautische e-mail sturen (berichten van domeinen die niet voldoen aan SPF-, DKIM- of DMARC-controles) en deze afzenders handmatig toestaan.

Door bekende afzenders toe te staan vervalste berichten te verzenden vanaf bekende locaties, kunt u fout-positieven verminderen (goede e-mail die als slecht is gemarkeerd). Door de toegestane vervalste afzenders te controleren, biedt u een extra beveiligingslaag om te voorkomen dat onveilige berichten in uw organisatie aankomen.

U kunt ook vervalste afzenders controleren die door spoofinformatie zijn toegestaan en deze afzenders handmatig blokkeren van het inzicht in spoof intelligence.

In de rest van dit artikel wordt uitgelegd hoe u het inzicht in spoof intelligence kunt gebruiken in het Security & Compliance Center en in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

> [!NOTE]
>
> - Alleen vervalste afzenders die door spoof intelligence zijn gedetecteerd, worden weergegeven in het inzicht van de spoof intelligence. Wanneer u de uitspraak toestaan of blokkeren overschrijven in het inzicht, wordt de vervalste afzender een handmatige invoer toestaan of blokkeren die alleen wordt weergegeven op het tabblad **Spoof** in de lijst Tenant toestaan/blokkeren. U kunt ook handmatig vermeldingen voor vervalste afzenders maken of blokkeren voordat ze worden gedetecteerd door spoofinformatie. Zie De lijst Tenant [toestaan/blokkeren beheren in EOP](tenant-allow-block-list.md)voor meer informatie.
>
> - Het inzicht in spoof intelligence en het tabblad **Spoof** in de lijst Tenant Allow/Block vervangen de functionaliteit van het spoof intelligence-beleid dat beschikbaar was op de pagina antispambeleid in het Beveiligings- & Compliancecentrum.
>
>- Het inzicht in spoof intelligence toont 7 dagen aan gegevens. De **get-SpoofIntelligenceInsight-cmdlet** toont 30 dagen aan gegevens.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **pagina Anti-phishing wilt** gaan, gebruikt u <https://protection.office.com/antiphishing> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u het spoof intelligence-beleid wilt wijzigen of spoofinformatie wilt in- of uitschakelen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot het spoof intelligence-beleid moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- U schakelt spoofinformatie in en uit in anti-phishingbeleid in EOP en Microsoft Defender voor Office 365. Spoofinformatie is standaard ingeschakeld. Zie [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md) of [Anti-phishingbeleid configureren in Microsoft Defender](configure-atp-anti-phishing-policies.md)voor Office 365.

- Zie Standaardinstellingen voor [anti-phishingbeleid](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)van EOP voor onze aanbevolen instellingen voor spoofinformatie.

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>Het inzicht in spoof intelligence openen in het beveiligings- & compliancecentrum

1. Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Op de **hoofdpagina Anti-phishing heeft** het inzicht in spoof intelligence twee modi:

   - **Insight-modus:** Als spoof intelligence is ingeschakeld, wordt in het inzicht duidelijk hoeveel berichten de afgelopen zeven dagen zijn gedetecteerd door spoof intelligence.
   - **Wat als de modus**: Als spoof intelligence is  uitgeschakeld, wordt in het inzicht duidelijk hoeveel berichten de afgelopen zeven dagen door spoof intelligence zijn gedetecteerd.

   Hoe dan ook, de vervalste domeinen die in het inzicht worden weergegeven, zijn onderverdeeld in twee categorieën: **Verdachte** domeinen en **Niet-verdachte domeinen.**

   - **Verdachte domeinen zijn:**

     - Spoof met veel vertrouwen: op basis van de historische verzendingspatronen en de reputatiescore van de domeinen, zijn we ervan overtuigd dat de domeinen spoofing zijn en dat berichten uit deze domeinen waarschijnlijk schadelijk zijn.

     - Matig vertrouwen spoof: Op basis van historische verzendende patronen en de reputatiescore van de domeinen, zijn we er redelijk zeker van dat de domeinen spoofing zijn en dat berichten die vanuit deze domeinen worden verzonden legitiem zijn. False positives zijn waarschijnlijker in deze categorie dan spoof met veel vertrouwen.

   **Niet-verdachte domeinen:** het domein is mislukt expliciete e-mailverificatie [controleert SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC](use-dmarc-to-validate-email.md)). Het domein is echter geslaagd voor onze impliciete e-mailverificatiecontroles[(samengestelde verificatie).](email-validation-and-authentication.md#composite-authentication) Hierdoor is er geen anti-spoofing actie ondernomen op het bericht.

### <a name="view-information-about-spoofed-messages"></a>Informatie over vervalste berichten weergeven

Klik op het inzicht in spoof intelligence op **Verdachte domeinen** of **Niet-verdachte** domeinen om naar de pagina Inzicht in **spoofinformatie te** gaan. De pagina bevat de volgende informatie:

- **Vervalst domein:** het domein van de vervalste gebruiker die wordt weergegeven in het vak **Van** in e-mail clients. Dit adres wordt ook wel het adres `5322.From` genoemd.
- **Infrastructuur:** ook wel de _verzendende infrastructuur genoemd._ Dit is een van de volgende waarden:
  - Het domein dat is gevonden in een REVERSE DNS lookup (PTR-record) van het IP-adres van de bron-e-mailserver.
  - Als het bron-IP-adres geen PTR-record heeft, wordt de verzendende infrastructuur geïdentificeerd als \<source IP\> /24 (bijvoorbeeld 192.168.100.100/24).
- **Aantal berichten:** het aantal berichten van de  combinatie van het vervalste domein en de verzendende infrastructuur naar uw organisatie in de afgelopen 7 dagen.
- **Laatst gezien:** De laatste datum waarop een bericht is ontvangen van de verzendende infrastructuur met het vervalste domein.
- **Type spoof:** Een van de volgende waarden:
  - **Intern:** De vervalste afzender is een domein dat deel uitmaken van uw organisatie (een [geaccepteerd domein).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
  - **Extern:** De vervalste afzender is een extern domein.
- **Toegestaan om te spoofen:** de  waarde is afhankelijk van of u op Verdachte domeinen of **Niet-verdachte** domeinen hebt geklikt op het inzicht:
  - **Verdachte domeinen:** De **toegestane waarde voor spoofing** is altijd **Nee.** Berichten uit de combinatie van het vervalste domein en _de_ verzendende infrastructuur worden als slecht gemarkeerd door spoofinformatie. De actie die wordt ondernomen op de vervalste berichten, wordt bepaald door het standaard anti-phishingbeleid of het aangepaste anti-phishingbeleid (de standaardwaarde is Bericht verplaatsen naar map **Ongewenste e-mail).** Zie [Anti-phishingbeleid configureren in Microsoft Defender](configure-atp-anti-phishing-policies.md)voor Office 365.
  - **Niet-verdachte domeinen:** De **toegestane waarde voor spoofing** is altijd **Ja.** Berichten uit de combinatie van het vervalste domein en _de_ verzendende infrastructuur worden gemarkeerd als goed door spoof intelligence.

U kunt op geselecteerde kolomkoppen klikken om de resultaten te sorteren.

Als u de resultaten wilt filteren, hebt u de volgende opties:

- Gebruik het **vak Filter spoofed domain** om een door komma's gescheiden lijst met vervalste domeinwaarden in te voeren om de resultaten te filteren.
- Gebruik het **vak Filterinfrastructuur** om een door komma's gescheiden lijst met infrastructuurwaarden in te voeren om de resultaten te filteren.
- Klik op **de knop Filter** om de resultaten te filteren op **spooftype.**

### <a name="view-details-about-spoofed-messages"></a>Details over vervalste berichten weergeven

Selecteer een item in de lijst om details weer te geven. Er wordt een flyout weergegeven met de volgende informatie en functies:

- **Toegestaan om te spoofen:** Gebruik deze schakelknop om de spoof intelligence-uitspraak te overschrijven:
  - Als u oorspronkelijk Verdachte domeinen in **het inzicht** hebt geselecteerd, is Toegestaan om **te spoofen** uitgeschakeld. Als u het item wilt in- of uitschakelen, waardoor het item wordt verplaatst van het inzicht in de spoofintelligentie naar de tenantlijst toestaan/blokkeren als een toegestane vermelding voor spoof, schuift u de schakelknop in op: Schakel de schakelknop ![ ](../../media/scc-toggle-on.png) in.
  - Als u oorspronkelijk **Niet-verdachte** domeinen hebt geselecteerd in het inzicht, is Toegestaan om **te spoofen** ingeschakeld. Als u het item wilt uitschakelen, waardoor het item wordt verplaatst van het inzicht in de spoofintelligentie naar de Tenant Allow/Block List als blokinvoer voor spoof, schuift u de schakelknop uit: Schakel de schakelknop ![ ](../../media/scc-toggle-off.png) uit.

- Waarom we dit hebben gesnapt.
- Wat u moet doen.
- Een domeinoverzicht met de meeste van dezelfde informatie op de hoofdpagina met spoofinformatie.
- WhoIs-gegevens over de afzender.
- Soortgelijke berichten die we hebben gezien in uw tenant van dezelfde afzender.

### <a name="about-allowed-spoofed-senders"></a>Over toegestane vervalste afzenders

Een toegestane vervalste afzender in **Niet-verdachte** domeinen in het inzicht van spoof intelligence of een geblokkeerde afzender **in** verdachte domeinen die u handmatig hebt gewijzigd in Toegestaan om **te spoofen,** staat alleen berichten toe van de combinatie van het vervalste *domein* en de verzendende infrastructuur. E-mail van het vervalste domein is niet toegestaan vanuit een bron en ook geen e-mail van de verzendende infrastructuur voor een domein.

De volgende vervalste afzender mag bijvoorbeeld spoofen:

- **Domein:** gmail.com
- **Infrastructuur**: tms.mx.com

Alleen e-mail van dat domein/verzendende infrastructuurpaar mag spoofen. Andere afzenders die proberen te spoofen gmail.com zijn niet automatisch toegestaan. Berichten van afzenders in andere domeinen die afkomstig zijn van tms.mx.com worden nog steeds gecontroleerd door spoof intelligence en kunnen worden geblokkeerd.

## <a name="use-the-spoof-intelligence-insight-in-exchange-online-powershell-or-standalone-eop-powershell"></a>Het inzicht in spoof intelligence gebruiken in Exchange Online PowerShell of zelfstandige EOP PowerShell

In PowerShell gebruikt u de **cmdlet Get-SpoofIntelligenceInsight** om toegestane en geblokkeerde vervalste afzenders weer te geven die zijn gedetecteerd door spoofinformatie.  Als u de vervalste afzenders handmatig wilt toestaan of blokkeren, moet u de cmdlet **New-TenantAllowBlockListSpoofItems** gebruiken. Zie PowerShell gebruiken om de lijst [Tenant toestaan/blokkeren](tenant-allow-block-list.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list)te configureren voor meer informatie.

Voer de volgende opdracht uit om de informatie in het inzicht van de spoof intelligence te bekijken:

```powershell
Get-SpoofIntelligenceInsight
```

Zie [Get-SpoofIntelligenceInsight (Get-SpoofIntelligenceInsight)](/powershell/module/exchange/get-spoofintelligenceinsight)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Andere manieren om spoofing en phishing te beheren

Wees zorgvuldig met spoofing en phishingbeveiliging. Hier zijn verwante manieren om te controleren op afzenders die uw domein vervalsen en te voorkomen dat ze uw organisatie beschadigen:

- Controleer het **spoof-e-mailrapport.** U kunt dit rapport vaak gebruiken om vervalste afzenders weer te geven en te beheren. Zie Rapport [Spoofdetecties voor meer informatie.](view-email-security-reports.md#spoof-detections-report)

- Controleer de SPF-configuratie (Sender Policy Framework). Zie voor een korte introductie van SPF en om het snel te configureren [SPF in Microsoft 365 instellen om spoofing te voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Voor een beter begrip van hoe Office 365 gebruikmaakt van SPF of voor het oplossen van problemen of niet-standaardimplementaties zoals hybride implementaties, begint u met [Hoe Office 365 gebruikmaakt van SPF (Sender Policy Framework) om spoofing te voorkomen](how-office-365-uses-spf-to-prevent-spoofing.md).

- Controleer de DKIM-configuratie (DomainKeys Identified Mail). U moet DKIM naast SPF en DMARC gebruiken om te voorkomen dat aanvallers berichten verzenden die eruit zien alsof ze afkomstig zijn van uw domein. Met DKIM kunt u een digitale handtekening toevoegen aan e-mailberichten in de berichtkop. Zie [DKIM gebruiken om uitgaande](use-dkim-to-validate-outbound-email.md)e-mail te valideren die is verzonden vanuit uw aangepaste domein in Office 365.

- Controleer uw DMARC-configuratie (Domain-based Message Authentication, Reporting, and Conformance). De implementatie van DMARC met SPF en DKIM biedt extra bescherming tegen adresvervalsing en phishing-email. DMARC helpt ontvangende e-mailsystemen vast te stellen wat er moet gebeuren met berichten die zijn verzonden vanuit uw domein die niet door de SPF- en DKIM-controles komen. Zie [DMARC gebruiken om e-mail te](use-dmarc-to-validate-email.md)valideren in Office 365.
