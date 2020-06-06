---
title: Uw zelfstandige EOP-service instellen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Beheerders kunnen leren hoe ze standalone Exchange Online Protection (EOP) kunnen instellen om on-premises e-mailomgevingen te beschermen.
ms.openlocfilehash: b50ec7e2bca3765bb81e165b74596155da1f7940
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588062"
---
# <a name="set-up-your-standalone-eop-service"></a>Uw zelfstandige EOP-service instellen

In dit onderwerp wordt uitgelegd hoe u standalone Exchange Online Protection (EOP) instelt. Als u hier bent geland vanuit de wizard Office 365-domeinen, gaat u terug naar de wizard Office 365-domeinen als u Exchange Online Protection niet wilt gebruiken. Zie [E-mailstroom configureren met connectoren in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)als u op zoek bent naar meer informatie over het configureren van connectoren.

> [!NOTE]
> In dit onderwerp wordt ervan uitgegaan dat u on-premises mailboxen hebt en dat u deze wilt beschermen met EOP, dat bekend staat als een op zichzelf staand scenario. Als u al uw postvakken in de cloud wilt hosten met Exchange Online, hoeft u niet alle stappen in dit onderwerp te voltooien. Ga naar [Exchange Online-abonnementen vergelijken](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) om u aan te melden en cloudpostvakken te kopen. Als u een aantal van uw postvakken ter plaatse wilt hosten en sommige in de cloud, wordt dit een hybride scenario genoemd. Het vereist meer geavanceerde e-mail-flow-instellingen. [Met hybride implementaties](https://docs.microsoft.com/exchange/exchange-hybrid) van Exchange Server wordt uitgelegd dat de hybride e-mailstroom wordt uitgelegd en zijn koppelingen gekoppeld aan resources die laten zien hoe deze moet worden ingesteld.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Geschatte tijd om deze taak te voltooien: 1 uur

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. U hebt specifiek de rol Externe en geaccepteerde domeinen nodig, die standaard is toegewezen aan de rolgroepen MailFlowAdministrator en OrganizationManagement (global admins). Zie [Machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en Gebruik de EAC voor meer informatie [de lijst met leden in rolgroepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)wijzigen.

- Als u zich nog niet hebt aangemeld voor EOP, gaat u naar [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) en kiest u ervoor om de service te kopen of uit te proberen.

- Zie [Sneltoetsen voor het Exchange-beheercentrum in Exchange Online voor](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Heb je problemen? Vraag om hulp in het [Exchange Online Protection-forum.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Stap 1: Gebruik het Microsoft 365-beheercentrum om uw domein toe te voegen en te verifiëren

1. Ga in het [Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/admin-overview/about-the-admin-center)naar **Setup** om uw domein aan de service toe te voegen.

2. Volg de stappen om de toepasselijke DNS-records toe te voegen aan uw DNS-hostingprovider om het eigendom van het domein te verifiëren.

> [!TIP]
> [Voeg een domein toe aan Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) en [DNS-records maken bij een DNS-hostingprovider voor Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) zijn nuttige bronnen om te verwijzen naarmate u uw domein toevoegt aan de service en DNS configureert.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Stap 2: Ontvangers toevoegen en eventueel DBEB inschakelen

Voordat u uw e-mail configureert om van en naar de EOP-service te stromen, raden we u aan uw ontvangers aan de service toe te voegen. Er zijn verschillende manieren waarop u dit doen, zoals gedocumenteerd in [EOP beheren.](manage-mail-users-in-eop.md) Als u Directory Based Edge Blocking (DBEB) wilt inschakelen om verificatie van ontvangers binnen de service af te dwingen nadat u uw ontvangers hebt toegevoegd, moet u uw domeintype instellen op Gezaghebbend. Zie Directory Based Edge [Blocking gebruiken om berichten die naar ongeldige ontvangers zijn verzonden, te weigeren](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)voor meer informatie over DBEB.

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Stap 3: De EAC gebruiken om e-mailstroom in te stellen

Maak connectoren in het Exchange-beheercentrum (EAC) waarmee e-mailstroom tussen EOP en uw on-premises e-mailservers mogelijk is. Zie [Connectors instellen voor het routeren van e-mail tussen Microsoft 365 en uw eigen e-mailservers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)voor gedetailleerde instructies.

### <a name="how-do-you-know-this-task-worked"></a>Hoe weet je dat deze taak werkte?

Controleer de e-mailstroom tussen de service en uw omgeving. Zie [E-mailstroom testen door uw Microsoft 365-connectoren te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)voor meer informatie.

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Stap 4: Inkomende poort 25 SMTP-toegang toestaan

Nadat u connectors hebt geconfigureerd, wacht u 72 uur om de verspreiding van uw DNS-recordupdates toe te staan. Beperk hierna het binnenkomende SMTP-verkeer op uw firewall of e-mailservers om alleen e-mail te accepteren vanuit de EOP-datacenters, met name vanaf de IP-adressen die worden vermeld op [IP-adressen](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)van Exchange Online Protection . Dit beschermt uw on-premises omgeving door het bereik van binnenkomende berichten die u ontvangen te beperken. Als u bovendien instellingen op uw e-mailserver hebt die de IP-adressen beheren die verbinding mogen maken voor e-mailrelay, werkt u deze instellingen ook bij.

> [!TIP]
> Configureer instellingen op de SMTP-server met een verbindingstijd van 60 seconden. Deze instelling is aanvaardbaar voor de meeste situaties, waardoor enige vertraging in het geval van een bericht verzonden met een grote bijlage, bijvoorbeeld.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Stap 5: Ervoor zorgen dat spam wordt doorgestuurd naar de map Ongewenste e-mail van elke gebruiker

Om ervoor te zorgen dat spam (ongewenste e-mail) correct wordt doorgestuurd naar de map Ongewenste e-mail van elke gebruiker, moet u een aantal configuratiestappen uitvoeren. De stappen worden gegeven in [Zelfstandige EOP configureren om spam te leveren aan de map Ongewenste e-mail in hybride omgevingen.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)

Als u geen berichten wilt verplaatsen naar de map Ongewenste e-mail van elke gebruiker, u een andere actie kiezen door uw antispambeleid te bewerken. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Stap 6: Gebruik het Microsoft 365-beheercentrum om uw MX-record op EOP te richten

Volg de domeinconfiguratiestappen om uw MX-record voor uw domein bij te werken, zodat uw binnenkomende e-mail via EOP stroomt. Zorg ervoor dat u uw MX-record rechtstreeks op EOP richt, in tegenstelling tot het hebben van een filterservice van derden die e-mail doorgeeft aan EOP. Voor meer informatie u opnieuw verwijzen naar [DNS-records maken voor Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

> [!NOTE]
> Zie [Uitgebreide filtering voor connectoren in Exchange Online als](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)u uw MX-record moet aanwijzen op een andere server of service die voor EOP zit.

### <a name="how-do-you-know-this-task-worked"></a>Hoe weet je dat deze taak werkte?

Op dit moment hebt u de servicelevering geverifieerd voor een goed geconfigureerde outbound on-premises connector en hebt u geverifieerd dat uw MX-record naar EOP verwijst. U er nu voor kiezen om de volgende aanvullende tests uit te voeren om te controleren of een e-mail door de service wordt geleverd aan uw on-premises omgeving:

- Controleer de e-mailstroom tussen de service en uw omgeving. Zie [E-mailstroom testen door uw Microsoft 365-connectoren te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)voor meer informatie.

- Stuur een e-mailbericht van een webaccount naar een e-mailontvanger in uw organisatie waarvan het domein overeenkomt met het domein dat u aan de service hebt toegevoegd. Bevestig de levering van het bericht aan het on-premises postvak met Microsoft Outlook of een andere e-mailclient.

- Als u een uitgaande e-mailtest wilt uitvoeren, u een e-mailbericht van een gebruiker in uw organisatie naar een webaccount sturen en bevestigen dat het bericht is ontvangen.

> [!TIP]
> Wanneer u uw installatie hebt voltooid, hoeft u geen extra stappen uit te voeren om EOP spam en malware te laten verwijderen. EOP verwijdert spam en malware automatisch. U uw instellingen echter afstemmen op uw bedrijfsvereisten. Zie [Anti-spam- en anti-malwarebeveiliging in Office 365](anti-spam-and-anti-malware-protection.md) en [Spoofinformatie configureren](learn-about-spoof-intelligence.md)voor meer informatie. <br/><br/> Nu uw service wordt uitgevoerd, raden we u aan aanbevolen procedures te lezen [voor het configureren van EOP,](best-practices-for-configuring-eop.md)waarin aanbevolen instellingen en overwegingen worden beschreven voor nadat u EOP hebt ingesteld.
