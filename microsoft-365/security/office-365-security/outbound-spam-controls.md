---
title: Beveiliging tegen uitgaande spam
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie lezen over de uitgaande spam besturing in Exchange Online Protection (EOP) en wat u moet doen als u grootschalige mailings moet verzenden.
ms.openlocfilehash: 1097b768b955f2fa99c552ceda7564bef33a1aa7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202385"
---
# <a name="outbound-spam-protection-in-eop"></a>Beveiliging van uitgaande spam in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) van Exchange Online Eén klant die op een opzettelijke of onbedoelde hoeveelheid ongewenste e-mail van de organisatie uitzendt, kan de reputatie van de hele service nadelig beïnvloeden en kan van invloed zijn op de bezorging van andere klanten.

In dit onderwerp worden de besturingselementen en meldingen beschreven die zijn ontworpen om uitgaande spam te helpen voorkomen, en wat u kunt doen als u grootschalige mailings moet verzenden.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Wat beheerders kunnen doen om uitgaande spam te beheren

- **Ingebouwde meldingen gebruiken**: wanneer een gebruiker de verzending van een service of beleid voor [uitgaande spam](configure-the-outbound-spam-policy.md) beperkt en de e-mail beperkt blijft tegen [het](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) verzenden van e-mail, verzendt de standaard waarschuwings beleids de naam gebruiker die is **beperkt van het verzenden van e-mail** een melding per E-mail naar leden van de groep **TenantAdmins** (**algemene beheerders**). Zie [de instellingen voor meldingen voor gebruikers met beperkte toegang controleren](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)als u wilt configureren welke andere meldingen deze meldingen ontvangen. Daarnaast wordt in de standaard waarschuwings beleidsregels met de naam **limiet e-mail verzenden overschreden** en **verdacht verdachte patronen** voor het verzenden van e-mail verzonden naar leden van de groep **TenantAdmins** (**algemene beheerders**). Zie voor meer informatie over waarschuwingsbeleid, [Waarschuwingsbeleid in het beveiligings- en compliancecentrum](../../compliance/alert-policies.md).

- **Spam klachten van externe e-mail providers weergeven**: veel e-mailservices zoals Outlook.com, Yahoo en AOL geven een feedback herhalingslus waarbij indien een willekeurige gebruiker in hun dienst een e-mailbericht van microsoft 365 als spam markeert, wordt het bericht ingepakt en naar ons verzonden voor revisie. Ga voor meer informatie over de ondersteuning van de afzender voor Outlook.com naar <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Hoe EOP de uitgaande spam beheert

- **Scheiding van uitgaande e-mail verkeer**: elk uitgaand bericht dat via de service wordt verzonden, wordt gescand op spam. Als het bericht is afgeleid van spam, wordt dit afgeleverd via een secundaire, minder betrouwbare IP-adresgroep genaamd de _bezorgings groep voor hoog risico_. Zie voor meer informatie de [groep hoog risico voor uitgaande berichten](high-risk-delivery-pool-for-outbound-messages.md).

- **Monitoring van de bron-IP-adres reputatie**: microsoft 365 vraagt diverse IP-blok lijsten van derden. Er wordt een waarschuwing gegenereerd als een van de IP-adressen die worden gebruikt voor uitgaande e-mail, op deze lijsten wordt weergegeven. Dit kan we snel reageren wanneer spam onze reputatie heeft ontcijferd. Wanneer een waarschuwing wordt gegenereerd, hebben we interne documentatie met informatie over hoe u onze IP-adressen (uit de lijst met geblokkeerde nummers) van blok lijsten kunt verwijderen.

- Sta **accounts uit die te veel spam verzenden** <sup>\*</sup> : hoewel ze uitgaande spam verdeelt in de groep voor hoog-risico levering, kunnen we een account (vaak geen gemanipuleerd account) toestaan om ongewenste e-mail te verzenden. We volgen accounts die spam verzenden en wanneer ze een niet-geopenbaarte limiet overschrijden, kunnen het verzenden van e-mail blokkeren. Er gelden verschillende drempelwaarden voor afzonderlijke gebruikers en de volledige Tenant.

- **Accounts die te veel e-mail versturen te snel verzenden** <sup>\*</sup> : naast de limieten voor berichten die zijn gemarkeerd als spam, gelden er ook beperkingen voor het blokkeren van geblokkeerde accounts wanneer ze een algemene uitgaande bericht limiet bereiken, ongeacht de spamfilter verdict voor uitgaande berichten. Een gemanipuleerd account kan met een onherkenbare spam (eerder niet herkend) spam verzenden die niet is gemist met het spamfilter. Aangezien het lastig is om een legitieme grootschalige mailings campagne te identificeren versus een spam campagne, kunnen deze limieten helpen om eventuele schade te minimaliseren.

<sup>\*</sup> We promoten de exacte grenzen niet zodat spammers het systeem niet kunnen zien, zodat we de limieten zo nodig kunnen vergroten of verkleinen. De limieten zijn hoog genoeg om te voorkomen dat een gemiddelde zakelijke gebruiker ooit deze mag overschrijden, en bijna genoeg genoeg voor de schade die door een spammer wordt veroorzaakt.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Aanbevelingen voor klanten die grootschalige mailings willen verzenden via EOP

U kunt zich moeilijk een saldo betrekken tussen klanten die een groot volume e-mailbericht willen verzenden en de service beschermen tegen gemanipuleerde accounts en bulksgewijze e-mail afzenders met slechte geadresseerden. De kosten van een e-mailadres van een Microsoft 365-e-mail bron in een lijst met IP-blok lijsten van derden zijn groter dan het blokkeren van een gebruiker die te veel e-mail verzendt.

Zoals beschreven in de [servicebeschrijving van Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), met behulp van EOP voor het verzenden van bulk-e-mail, is geen ondersteund gebruik van de service en wordt alleen toegestaan voor de ' Best effort '-basis. Voor klanten die bulkmail willen verzenden, adviseren we de volgende oplossingen:

- **Verstuur bulk berichten via on-premises e-mailservers**: Dit betekent dat klanten hun eigen e-mailinfrastructuur voor grootschalige mailings moeten onderhouden.

- **Gebruik een bulk provider voor bulk**mail van derden: er zijn diverse leveranciers van oplossingen voor bulkmail die u kunt gebruiken voor het verzenden van grootschalige mailings. Deze bedrijven hebben een uitoefenbare interesse voor het werken met klanten en garanderen een goede manier om e-mailberichten te verzenden.

Met de chatfunctie berichten, mobiel en malware die anti-spam werken, wordt het lidmaatschaps schema van de malware gepubliceerd <https://www.maawg.org/about/roster> . Meerdere leveranciers voor bulkmail bevinden zich in de lijst en zijn bekend als de verantwoordelijke Internet burgers.
