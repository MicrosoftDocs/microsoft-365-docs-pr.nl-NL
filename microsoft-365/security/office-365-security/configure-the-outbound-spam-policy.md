---
title: Het uitgaande spambeleid configureren
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: Uitgaande spamfiltering is altijd ingeschakeld als u de service gebruikt voor het verzenden van uitgaande e-mail, waardoor organisaties worden beschermd die de service en de beoogde ontvangers gebruiken.
ms.openlocfilehash: 0fa5ec23eee6144864f16b52d452d02f38b554d7
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2020
ms.locfileid: "42805286"
---
# <a name="configure-the-outbound-spam-policy"></a>Het uitgaande spambeleid configureren

Uitgaande spamfiltering is altijd ingeschakeld als u de service gebruikt voor het verzenden van uitgaande e-mail, waardoor organisaties worden beschermd die de service en de beoogde ontvangers gebruiken. Net als in binnenkomende filtering bestaat uitgaande spamfiltering uit verbindingsfiltering en inhoudsfiltering en kunnen sommige specifieke besturingselementen uitgaande berichten verwerken. Typen verouderde beleidsinstellingen voor spamfilters:

- Standaard: het standaard beleid voor uitgaande spamfilters wordt gebruikt om de instellingen voor uitgaande spamfilters in het hele bedrijf te configureren. Dit beleid kan niet worden hernoemd en is altijd ingeschakeld.

- Aangepast: aangepast uitgaande spamfilterbeleid kan gedetailleerd zijn en worden toegepast op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepaste beleidsregels hebben altijd voorrang op het standaardbeleid. U de volgorde wijzigen waarin uw aangepaste beleidsregels worden uitgevoerd door de prioriteit van elk aangepast beleid te wijzigen. Alleen het beleid met de hoogste prioriteit (d.w.z. nummer dat het dichtst bij 0 ligt) is echter van toepassing als de gebruiker meerdere beleidsregels aanpast.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?
<a name="sectionSection0"> </a>

- Geschatte tijd om te voltooien: 5 minuten

- U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie de vermelding 'Antispam-item in het onderwerp [Functiemachtigingen in Exchange Online'](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) om te zien welke machtigingen u nodig hebt.

- U de procedures in dit onderwerp ook uitvoeren in externe PowerShell. Gebruik de cmdlet [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) om uw instellingen te bekijken en het [beleid voor het beleid voor extern](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) spamfilter instellen om uw instellingen voor het binnenkomende spambeleid te bewerken.

  Zie Verbinding maken met [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)als u verbinding wilt maken met Exchange Online PowerShell. Zie Verbinding maken met [PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)voor de beveiliging van Exchange Online.

## <a name="use-the-security--compliance-center-scc-to-edit-the-default-outbound-spam-policy"></a>Het Security & Compliance Center (SCC) gebruiken om het standaard uitgaande spambeleid te bewerken

Gebruik de volgende procedure om het standaard uitgaande spambeleid te bewerken:

### <a name="to-configure-the-default-outbound-spam-policy"></a>Het standaard binnenkomende spambeleid configureren

1. Navigeer in de SCC naar **antispam** **van** \> het beleid **voor bedreigingsbeheer** \>

2. Vouw de sectie **Uitgaande spamfilterbeleid (altijd AAN)** uit en klik op **Beleid bewerken**.

3. Vouw de sectie **Meldingen** uit en selecteer de volgende selectievakjes met betrekking tot uitgaande berichten en selecteer **Vervolgens Personen** toevoegen om een gekoppeld e-mailadres of adressen toe te voegen in het bijbehorende dialoogvenster. (dit kunnen distributielijsten zijn als ze worden opgelost als geldige SMTP-bestemmingen):

   - **Stuur een kopie van alle verdachte uitgaande e-mailberichten naar het volgende e-mailadres of de volgende adressen:** Dit zijn berichten die door het filter als spam zijn gemarkeerd (ongeacht de SCL-beoordeling). Ze worden niet afgewezen door het filter, maar worden door de leveringspool met een hoger risico gerouteerd. Scheid meerdere adressen met een puntkomma. Houd er rekening mee dat de opgegeven ontvangers de berichten ontvangen als een Bcc-adres (Van en naar) (de velden Van en naar zijn de oorspronkelijke afzender en ontvanger).

   - **Stuur een melding naar het volgende e-mailadres wanneer een afzender wordt geblokkeerd**het verzenden van uitgaande spam : Afzonderlijke meerdere adressen met een puntkomma.

   Wanneer een aanzienlijke hoeveelheid spam of andere verzendafwijkingen van een bepaalde gebruiker wordt gedetecteerd, is het de gebruiker beperkt tot het verzenden van e-mailberichten en wordt een melding verzonden naar de opgegeven e-mailadressen.

   De beheerder van het domein, die is opgegeven met behulp van deze instelling, wordt geïnformeerd dat uitgaande berichten worden geblokkeerd voor deze gebruiker.  Zie [Voorbeeldmelding wanneer een afzender wordt geblokkeerd](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)om uitgaande spam te verzenden om te zien hoe deze melding eruit ziet.

   > [!NOTE]
   > Er wordt ook een systeemwaarschuwing gegenereerd die aangeeft dat de gebruiker is beperkt. Zie Een gebruiker verwijderen uit de portal [Beperkte gebruikers verwijderen na het verzenden van spam-e-mail](removing-user-from-restricted-users-portal-after-spam.md)voor meer informatie over de waarschuwing en hoe u de gebruiker herstellen.

4. Vouw de sectie **Geadresseerde limieten** uit om het maximumaantal ontvangers op te geven dat een gebruiker kan verzenden, per uur voor interne en externe ontvangers, samen met het maximumaantal per dag.

   > [!NOTE]
   > Het maximum aantal voor elke invoer is 10000. Zie limieten [voor ontvangen en verzenden binnen Exchange online voor](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) meer informatie

7. Geef de **actie** op die moet worden ondernomen wanneer een gebruiker de opgegeven limieten overschrijdt.  De acties die mogelijk zijn zijn als volgt:

   - **Beperk de gebruiker om e-mail te verzenden tot de volgende dag**.  Zodra een verzendlimiet is overschreden (intern, extern of dagelijks) wordt een waarschuwing gegenereerd voor de beheerder en kan de gebruiker geen verdere e-mail verzenden tot de volgende dag, op basis van UTC-tijd. Er is geen manier voor de beheerder om dit blok te overschrijven.

   - **Beperk de gebruiker om e-mail te verzenden**.  Zodra een verzendlimiet is overschreden (intern, extern of dagelijks) wordt een waarschuwing gegenereerd voor de beheerder en kan de gebruiker geen verdere e-mail verzenden totdat de beheerder de beperking verwijdert.  In deze gevallen wordt de gebruiker vermeld op de [pagina Beperkte gebruikers](removing-user-from-restricted-users-portal-after-spam.md).  Eenmaal verwijderd uit de lijst wordt de gebruiker niet opnieuw beperkt voor die dag.

   - **Geen actie/waarschuwing alleen**. Zodra een verzendlimiet is overschreden (intern, extern of dagelijks) wordt een waarschuwing gegenereerd voor de beheerder, maar er wordt geen actie ondernomen om de gebruiker te beperken.

6. Vouw de sectie **Toepassen** uit en maak vervolgens een op voorwaarden gebaseerde regel om de gebruikers, groepen en domeinen op te geven waarop dit beleid kan worden toegepast. U meerdere voorwaarden maken, als ze uniek zijn.  Opmerking: dat gebruikers aan alle voorwaarden moeten voldoen wanneer meerdere voorwaarden zijn opgegeven.  

   - Als u gebruikers wilt selecteren, selecteert u **De afzender is**. Selecteer in het volgende dialoogvenster een of meer afzenders van uw bedrijf in de lijst gebruikerskiezer en klik op Toevoegen. Als u afzenders wilt toevoegen die niet in de lijst staan, typt u hun e-mailadressen en klikt u op Namen controleren. Wanneer u klaar bent met het maken van uw selecties, klikt u op ok om terug te keren naar het hoofdscherm.

   - Als u groepen wilt selecteren, selecteert u **De afzender is lid van**. Selecteer of geef vervolgens in het volgende dialoogvenster de groepen op. Klik op Ok om terug te keren naar het hoofdscherm.

   - Als u domeinen wilt selecteren, selecteert u **Het afzenderdomein is**. Voeg vervolgens in het volgende dialoogvenster de domeinen toe. Klik op Ok om terug te keren naar het hoofdscherm.

   U uitzonderingen maken binnen de regel. U bijvoorbeeld berichten van alle domeinen filteren, behalve een bepaald domein. Klik op uitzondering toevoegen en maak vervolgens uw uitzonderingsvoorwaarden die vergelijkbaar zijn met de manier waarop u de andere voorwaarden hebt gemaakt.

   Het toepassen van een uitgaand spambeleid op een groep wordt alleen ondersteund voor beveiligingsgroepen met e-mail.

7. Klik **op Opslaan**.

## <a name="to-create-a-custom-policy-for-a-specific-set-of-users"></a>Een aangepast beleid maken voor een specifieke groep gebruikers

1. Navigeer in de SCC naar **antispam** **van** \> het beleid **voor bedreigingsbeheer** \>

2. Klik op de knop **Een uitgaand beleid** maken.

3. Vouw de sectie **Meldingen** uit en selecteer de volgende selectievakjes met betrekking tot uitgaande berichten en selecteer **Vervolgens Personen** toevoegen om een gekoppeld e-mailadres of adressen toe te voegen in het bijbehorende dialoogvenster.

4. Vouw de sectie **Geadresseerde limieten** uit om het maximumaantal ontvangers op te geven dat een gebruiker kan verzenden, per uur voor interne en externe ontvangers en het maximumaantal per dag.

7. Geef de **actie** op die moet worden ondernomen wanneer een gebruiker de opgegeven limieten overschrijdt.

6. Vouw de sectie **Toepassen** uit en maak een op voorwaarden gebaseerde regel om de gebruikers, groepen en domeinen op te geven waarop dit beleid moet worden toegepast. U meerdere voorwaarden maken, als ze uniek zijn.  

8. Klik **op Opslaan**

## <a name="for-more-information"></a>Voor meer informatie

[Een gebruiker verwijderen uit de portal Beperkte gebruikers na het verzenden van spam-e-mail](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[Een risicovolle leveringsgroep voor uitgaande berichten](high-risk-delivery-pool-for-outbound-messages.md)

[Veelgestelde vragen over antispambescherming](anti-spam-protection-faq.md)
