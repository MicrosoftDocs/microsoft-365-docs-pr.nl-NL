---
title: On-premises postvakken in China beveiligen met standalone EOP
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
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders in China die Office 365 gebruiken die door 21Vianet worden beheerd, kunnen leren hoe ze standalone Exchange Online Protection (EOP) kunnen gebruiken om hun on-premises mailboxen te beschermen.
ms.openlocfilehash: 3e9ba8400ce9c545dd26f2dadce70595f5c5695e
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587978"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>On-premises postvakken in China beveiligen met standalone EOP

> [!NOTE]
> Dit artikel is alleen van toepassing op Office 365 dat wordt beheerd door 21Vianet in China.

Zelfs als u van plan bent om sommige of alle postvakken on-premises te hosten, u de postvakken nog steeds beveiligen met Exchange Online Protection (EOP). Als u connectoren wilt configureren, moet uw account een globale beheerder of een beheerder van het Exchange-bedrijf zijn (de rolgroep Organisatiebeheer). Zie [Beheerdersrollen toewijzen in Office 365 die door 21Vianet worden beheerd voor](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet)informatie over de manier waarop machtigingen van Office 365 betrekking hebben op Exchange-machtigingen. Als al uw Exchange-postvakken on-premise zijn, voert u deze stappen uit om uw EOP-service in te stellen.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Stap 1: Gebruik het Microsoft 365-beheercentrum om uw domein toe te voegen en te verifiëren

1. Navigeer in het Microsoft 365-beheercentrum naar Setup om uw domein aan de service toe te voegen.

2. Volg de stappen in de portal om de toepasselijke DNS-records toe te voegen aan uw DNS-hostingprovider om het eigendom van het domein te verifiëren.

> [!TIP]
> [Voeg uw domein en gebruikers toe aan Office 365 dat wordt beheerd door 21Vianet](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet) en [DNS-records maken voor Office 365 wanneer u uw DNS-records beheert,](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet) zijn nuttige bronnen om te verwijzen naarmate u uw domein toevoegt aan de service en DNS configureert.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Stap 2: Geadresseerden toevoegen en het domeintype configureren

Voordat u uw e-mail configureert om van en naar de EOP-service te stromen, raden we u aan uw ontvangers aan de service toe te voegen. Er zijn verschillende manieren waarop u dit doen, zoals gedocumenteerd in [EOP beheren.](manage-mail-users-in-eop.md) Als u Directory Based Edge Blocking (DBEB) wilt inschakelen om verificatie van ontvangers binnen de service af te dwingen nadat u uw ontvangers hebt toegevoegd, moet u uw domeintype instellen op Gezaghebbend. Zie Directory Based Edge [Blocking gebruiken om berichten die naar ongeldige ontvangers zijn verzonden, te weigeren voor](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)meer informatie over DBEB.

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Stap 3: De EAC gebruiken om e-mailstroom in te stellen

Maak connectoren in het Exchange-beheercentrum (EAC) waarmee e-mailstroom tussen EOP en uw on-premises e-mailservers mogelijk is. Zie [E-mailstroom configureren met connectoren configureren in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)voor gedetailleerde instructies.

 Hoe weet je dat deze taak werkte?

 Zie [E-mailstroom testen door uw Office 365-connectors te valideren.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Stap 4: Inkomende poort 25 SMTP-toegang toestaan

Nadat u connectors hebt geconfigureerd, wacht u 72 uur om de verspreiding van uw DNS-recordupdates toe te staan. Beperk hierna binnenkomend poort-25 SMTP-verkeer op uw firewall of e-mailservers om alleen e-mail te accepteren vanuit de EOP-datacenters, met name vanaf de IP-adressen die worden vermeld bij [URL's en IP-adresbereiken voor Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints). Dit beschermt uw on-premises omgeving door het bereik van binnenkomende berichten die u ontvangen te beperken. Als u bovendien instellingen op uw e-mailserver hebt die de IP-adressen beheren die verbinding mogen maken voor e-mailrelay, werkt u deze instellingen ook bij.

> [!TIP]
> Configureer instellingen op de SMTP-server met een verbindingstijd van 60 seconden. Deze instelling is aanvaardbaar voor de meeste situaties, waardoor enige vertraging in het geval van een bericht verzonden met een grote bijlage, bijvoorbeeld.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Stap 5: Ervoor zorgen dat spam wordt doorgestuurd naar de map Ongewenste e-mail van elke gebruiker

Om ervoor te zorgen dat spam (ongewenste e-mail) correct wordt doorgestuurd naar de map Ongewenste e-mail van elke gebruiker, moet u een aantal configuratiestappen uitvoeren. De stappen worden gegeven in [Zelfstandige EOP configureren om spam te leveren aan de map Ongewenste e-mail in hybride omgevingen.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Als u geen berichten wilt verplaatsen naar de map Ongewenste e-mail van elke gebruiker, u een andere actie kiezen door uw antispambeleid (ook wel beleid voor inhoudsfilter genoemd) te bewerken. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Stap 6: Gebruik het Microsoft 365-beheercentrum om uw MX-record op EOP te richten

Volg de stappen voor de configuratie van office 365-domeinen om uw MX-record voor uw domein bij te werken, zodat uw binnenkomende e-mail via EOP stroomt. Voor meer informatie u opnieuw verwijzen naar [DNS-records maken voor Office 365 wanneer u uw DNS-records beheert.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)

Hoe weet je dat deze taak werkte?

 Zie [E-mailstroom testen door uw Office 365-connectors te valideren.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

Op dit moment hebt u de servicelevering geverifieerd voor een goed geconfigureerde outbound on-premises connector en hebt u geverifieerd dat uw MX-record naar EOP verwijst. U er nu voor kiezen om de volgende aanvullende tests uit te voeren om te controleren of een e-mail door de service wordt geleverd aan uw on-premises omgeving:

- Klik in de analyse van de externe connectiviteit op het tabblad **Office 365** en voer vervolgens de **inkomende SMTP-e-mailtest** uit onder **Internet-e-mailtests**.

- Stuur een e-mailbericht van een webaccount naar een e-mailontvanger in uw organisatie waarvan het domein overeenkomt met het domein dat u aan de service hebt toegevoegd. Bevestig de levering van het bericht aan het on-premises postvak met Microsoft Outlook of een andere e-mailclient.

- Als u een uitgaande e-mailtest wilt uitvoeren, u een e-mailbericht van een gebruiker in uw organisatie naar een webaccount sturen en bevestigen dat het bericht is ontvangen.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Minder vaak: een hybride installatie met postvakken on-premises en in de cloud

Als u Exchange-postvakken on-premises en een of meer postvakken in de cloud in Exchange Online hebt, hebt u een *hybride* installatie. In een hybride installatie werken functies zoals gratis/bezet delen van agenda's en e-mailroutering samen in uw on-premises en cloudomgevingen. Mogelijk hebt u een hybride installatie op zijn plaats terwijl u postvakken overzet naar Exchange Online. Een hybride omgeving is anders ingesteld dan EOP standalone bescherming.

U een hybride scenario kiezen om te profiteren van cloudgebaseerde e-mail voor de meeste van uw werknemers. U dit doen terwijl u ook een aantal postvakken on-premises hostt; bijvoorbeeld voor uw juridische afdeling.

Een hybride setup kan complex zijn, maar het heeft vele voordelen. Zie [Hybride implementaties](https://docs.microsoft.com/Exchange/exchange-hybrid)van Exchange Server voor meer informatie over het instellen van hybride scenario's met Exchange.
