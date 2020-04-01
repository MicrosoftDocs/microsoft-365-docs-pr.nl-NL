---
title: Uw EOP-service instellen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: In dit onderwerp wordt uitgelegd hoe u Microsoft Exchange Online Protection (EOP) instelt. Als u hier bent geland vanuit de wizard Office 365-domeinen, gaat u terug naar de wizard Office 365-domeinen als u Exchange Online-beveiliging niet wilt gebruiken. Zie E-mailstroom configureren met connectors in Office 365 als u meer informatie wilt over het configureren van connectors.
ms.openlocfilehash: 6686e95f343a116a53991957e7746ef841e858ba
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081230"
---
# <a name="set-up-your-eop-service"></a>Uw EOP-service instellen

In dit onderwerp wordt uitgelegd hoe u Microsoft Exchange Online Protection (EOP) instelt. Als u hier bent geland vanuit de wizard Office 365-domeinen, gaat u terug naar de wizard Office 365-domeinen als u Exchange Online-beveiliging niet wilt gebruiken. Zie [E-mailstroom configureren met connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)als u meer informatie wilt over het configureren van connectors.

> [!NOTE]
> In dit onderwerp wordt ervan uitgegaan dat u on-premises postvakken hebt en dat u ze wilt beveiligen met EOP, dat bekend staat als een zelfstandig scenario. Als u al uw postvakken in de cloud wilt hosten met Exchange Online, hoeft u niet alle stappen in dit onderwerp uit te voeren. Ga naar [Exchange Online-abonnementen vergelijken](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) om u aan te melden en cloudpostvakken aan te schaffen. Als u een aantal van uw postvakken op locatie en sommige in de cloud wilt hosten, wordt dit een hybride scenario genoemd. Het vereist meer geavanceerde mail-flow instellingen. [Hybride implementaties van Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid) leggen de hybride e-mailstroom uit en hebben koppelingen naar bronnen die laten zien hoe u deze instellen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Geschatte tijd om deze taak te voltooien: 1 uur

- Als u connectors wilt configureren, moet uw account een Globale beheerder van Office 365 of een Exchange Company Administrator (de rolgroep Organisatiebeheer) zijn. Zie [Functiemachtigingen in EOP](feature-permissions-in-eop.md)voor meer informatie.

- Als u zich nog niet hebt aangemeld voor EOP, gaat u naar [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) en kiest u ervoor om de service te kopen of te proberen.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp op het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Stap 1: Het Microsoft 365-beheercentrum gebruiken om uw domein toe te voegen en te verifiëren

1. Ga in het [Microsoft 365-beheercentrum](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)naar **Setup** om uw domein aan de service toe te voegen.

2. Volg de stappen om de toepasselijke DNS-records toe te voegen aan uw DNS-hostingprovider om het eigendom van het domein te verifiëren.

> [!TIP]
> [Een domein toevoegen aan Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) en [DNS-records maken bij elke DNS-hostingprovider voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) zijn nuttige bronnen om naar te verwijzen wanneer u uw domein toevoegt aan de service en DNS configureert.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Stap 2: Geadresseerden toevoegen en optioneel DBEB inschakelen

Voordat u uw e-mail configureert om van en naar de EOP-service te stromen, raden we u aan uw ontvangers aan de service toe te voegen. Er zijn verschillende manieren waarop u dit doen, zoals gedocumenteerd in [E-mailgebruikers beheren in EOP.](manage-mail-users-in-eop.md) Als u ook DBEB (Directory Based Edge Blocking) wilt inschakelen om de verificatie van ontvangers binnen de service af te dwingen nadat u uw geadresseerden hebt toegevoegd, moet u uw domeintype instellen op Gezaghebbend. Zie [Directory based edge blocking gebruiken om berichten die naar ongeldige geadresseerden worden verzonden, te weigeren](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)voor meer informatie over DBEB.

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Stap 3: De EAC gebruiken om de e-mailstroom in te stellen

Maak connectors in het Exchange-beheercentrum (EAC) waarmee e-mailstroom tussen EOP en uw on-premises e-mailservers mogelijk is. Zie [Connectors instellen voor het routeren van e-mail tussen Office 365 en uw eigen e-mailservers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)voor gedetailleerde instructies.

### <a name="how-do-you-know-this-task-worked"></a>Hoe weet je dat deze taak werkte?

Controleer de e-mailstroom tussen de service en uw omgeving. Zie [E-mailstroom testen door uw Office 365-connectors te valideren.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Stap 4: Inkomende poort 25 SMTP-toegang toestaan

Nadat u connectors hebt geconfigureerd, wacht u 72 uur om de verspreiding van uw DNS-recordupdates mogelijk te maken. Beperk hierna het inkomende poort-25 SMTP-verkeer op uw firewall of e-mailservers om alleen e-mail te accepteren vanuit de EOP-datacenters, met name vanaf de IP-adressen die worden vermeld op [IP-adressen](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)van Exchange Online Protection. Dit beschermt uw on-premises omgeving door het beperken van de reikwijdte van binnenkomende berichten die u ontvangen. Als u bovendien instellingen op uw e-mailserver hebt die de IP-adressen beheren die zijn toegestaan om verbinding te maken voor e-mailrelay, werkt u deze instellingen ook bij.

> [!TIP]
> Configureer instellingen op de SMTP-server met een verbindingstijd van 60 seconden. Deze instelling is acceptabel voor de meeste situaties, waardoor er bijvoorbeeld enige vertraging optreedt in het geval van een bericht dat met een grote bijlage wordt verzonden.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Stap 5: Ervoor zorgen dat spam wordt doorgestuurd naar de map Ongewenste e-mail van elke gebruiker

Om ervoor te zorgen dat spam (ongewenste e-mail) correct wordt doorgestuurd naar de map Ongewenste e-mail van elke gebruiker, moet u een paar configuratiestappen uitvoeren. De stappen zijn beschikbaar in [Standalone EOP configureren om spam te leveren aan de map Ongewenste e-mail in hybride omgevingen.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)

Als u geen berichten naar de map Ongewenste e-mail van elke gebruiker wilt verplaatsen, u een andere actie kiezen door uw inhoudsfilterbeleid te bewerken in het Exchange-beheercentrum. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Stap 6: Gebruik het Microsoft 365-beheercentrum om uw MX-record naar EOP te richten

Volg de stappen voor de configuratie van Office 365-domeinen om uw MX-record voor uw domein bij te werken, zodat uw binnenkomende e-mail via EOP verloopt. Zorg ervoor dat u uw MX-record rechtstreeks naar EOP richt in plaats van een e-mail met filterservice van derden naar EOP te sturen. Voor meer informatie u opnieuw verwijzen naar [DNS-records maken voor Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

### <a name="how-do-you-know-this-task-worked"></a>Hoe weet je dat deze taak werkte?

Op dit moment hebt u de servicelevering geverifieerd voor een goed geconfigureerde uitgaande on-premises connector en hebt u geverifieerd dat uw MX-record naar EOP wijst. U er nu voor kiezen om de volgende aanvullende tests uit te voeren om te controleren of een e-mail door de service wordt geleverd aan uw on-premises omgeving:

- Controleer de e-mailstroom tussen de service en uw omgeving. Zie [E-mailstroom testen door uw Office 365-connectors te valideren.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

- Stuur een e-mailbericht van een webgebaseerd e-mailaccount naar een e-mailontvanger in uw organisatie wiens domein overeenkomt met het domein dat u aan de service hebt toegevoegd. Bevestig de levering van het bericht in het on-premises postvak met Microsoft Outlook of een andere e-mailclient.

- Als u een uitgaande e-mailtest wilt uitvoeren, u een e-mailbericht van een gebruiker in uw organisatie naar een e-mailaccount op het web verzenden en bevestigen dat het bericht is ontvangen.

> [!TIP]
> Wanneer u uw installatie hebt voltooid, hoeft u geen extra stappen uit te voeren om EOP spam en malware te laten verwijderen. EOP verwijdert automatisch spam en malware. U uw instellingen echter in de EAC verfijnen op basis van uw zakelijke vereisten. Zie [Bescherming tegen spam en malwarebestrijding in Office 365](anti-spam-and-anti-malware-protection.md)voor meer informatie. <br/><br/> Nu uw service wordt uitgevoerd, raden we u aan [de aanbevolen procedures voor het configureren van EOP](best-practices-for-configuring-eop.md)te lezen, waarin aanbevolen instellingen en overwegingen worden beschreven voor nadat u EOP hebt ingesteld.
