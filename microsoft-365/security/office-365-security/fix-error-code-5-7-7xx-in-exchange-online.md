---
title: Problemen met e-mailbezorging oplossen voor foutcode 5.7.7xx in Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Meer informatie over het oplossen van e-mailproblemen voor foutcode 5.7.7xx in Exchange Online (tenant geblokkeerd voor het verzenden van e-mail).
ms.openlocfilehash: e8e134793db946ddfc3ef09d0adc19b2a04df30b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808802"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>Problemen met e-mailbezorging oplossen voor foutcode 5.7.7xx in Exchange Online

In dit onderwerp wordt beschreven wat u doen als u statuscode 550 5.7.7xx ziet in een rapport dat niet wordt geleverd (ook bekend als een NDR, bouncebericht, melding van de leveringsstatus of DSN). U ziet deze geautomatiseerde melding wanneer uw tenant op de een of andere manier geen e-mail mag verzenden. Deze foutcodes komen meestal binnen als 705 of 750.

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705: Huurder heeft drempelbeperking overschreden: Wat u moet weten

Zodra uw gebruikers (collectief, als organisatie) een bepaalde hoeveelheid verdachte e-mail via de service verzenden, kunnen alle gebruikers worden verhinderd om e-mail te verzenden totdat het probleem is opgelost. Dit is meestal het resultaat van een compromis (meest voorkomende) of het verzenden van te veel bulk post. Gebruikers ontvangen een NDR met als status:

`550 5.7.705 Access denied, tenant has exceeded threshold`

In zeldzame gevallen kan dit ook gebeuren als u uw abonnement verlengt nadat het al is verlopen. Het kost tijd voor de service om de nieuwe abonnementsinformatie te synchroniseren (meestal niet meer dan één dag), maar uw organisatie kan worden geblokkeerd om e-mail in de tussentijd te verzenden. De beste manier om dit te voorkomen is om ervoor te zorgen dat uw abonnement niet verloopt.

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750: Niet-geregistreerde domeine-mailbeperking: wat u moet weten

Met Office 365 kunnen tenants bepaalde berichten doorgeven via Exchange Online Protection (EOP). Bijvoorbeeld:

- Een Office 365-postvak ontvangt e-mail van een externe afzender. E-mail doorsturen is geconfigureerd in het Office 365-postvak, zodat het bericht teruggaat naar het externe e-mailadres van de gebruiker. Dit scenario komt het meest voor in onderwijsomgevingen waar studenten hun persoonlijke e-mailaccounts willen gebruiken om schoolgerelateerde berichten te bekijken.

- Hybride omgevingen met on-premises e-mailservers die uitgaande e-mail verzenden via EOP.

### <a name="problems-with-unregistered-domains"></a>Problemen met niet-geregistreerde domeinen

Het probleem is wanneer gecompromitteerd on-premises e-mailservers relais een groot volume van spam via EOP. In bijna alle gevallen worden de connectors correct ingesteld, maar e-mail wordt verzonden vanuit niet-geregistreerde (ook wel niet-ingerichte) domeinen genoemd. Office 365 staat een redelijke hoeveelheid e-mail toe van niet-geregistreerde domeinen, maar u moet elk domein configureren dat u gebruikt om e-mail te verzenden als een geaccepteerd domein.

Eenmaal gecompromitteerd, zullen huurders worden verhinderd uitgaande e-mail te verzenden voor niet-geregistreerde domeinen. Gebruikers ontvangen een NDR met als status:

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="unblocking-tenant-in-order-to-send-again"></a>Tenant deblokkeren om opnieuw te verzenden

Er zijn verschillende dingen die u moet doen als uw tenant is geblokkeerd voor het verzenden van e-mail:

1. Wijzig het wachtwoord voor uw beheerdersaccounts. Als een tenant is geblokkeerd voor het verzenden, is het zeer waarschijnlijk dat een beheerdersaccount is gecompromitteerd. Het wijzigen van wachtwoorden is de eerste stap om te voorkomen dat de aanvaller meer schade aanricht.

2. [Mfa inschakelen](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) voor alle beheerders in uw Office 365-organisatie.

3. Controleer of al uw e-maildomeinen zijn geregistreerd. Zie [Een domein toevoegen aan Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) en [Geaccepteerde domeinen beheren in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)voor meer informatie.

4. Zoek naar ongebruikelijke [connectoren.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) Kwaadwillenden maken vaak nieuwe binnenkomende connectors in uw Office 365-organisatie om spam te verzenden. Zie [Connectors valideren in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)als u uw bestaande connectors wilt weergeven.

5. Controleer op gecompromitteerde gebruikers zoals beschreven in [Reageren op een gecompromitteerd e-mailaccount in Office 365](responding-to-a-compromised-email-account.md).

6. Vergrendel uw on-premises e-mailservers en controleer of deze niet zijn gecompromitteerd.

   > [!TIP]
   > Er zijn veel factoren hier, vooral als je servers van derden gebruikt. Hoe dan ook, u moet controleren of uw uitgaande e-mail geen spam bevat.

7. Bel Microsoft Support en vraag om uw tenant te laten deblokkeren om e-mail opnieuw te verzenden. De foutcode is handig, maar u moet bewijzen dat uw omgeving is beveiligd en niet in staat is om spam te verzenden. Zie [Contactondersteuning voor zakelijke producten - Help voor beheerders](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)om een ondersteuningsaanvraag te openen.

## <a name="for-more-information"></a>Voor meer informatie

[Office 365 email anti-spam protection](anti-spam-protection.md)

[Richtlijnen voor bulkmail in het sectie verzendlimieten van de beschrijving van de Exchange Online-service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[Rapporten over niet-uitgevoerde bezorging e-mailen in Office 365 e-mail](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[Configure email forwarding for a mailbox](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)(Doorsturen van e-mail voor een postvak configureren)

[Een multifunctioneel apparaat of een toepassing instellen voor het verzenden van e-mail via Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

[Geaccepteerde domeinen beheren in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
