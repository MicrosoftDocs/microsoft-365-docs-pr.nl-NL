---
title: On-premises postvakken in China beveiligen met standalone EOP
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
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders in China met Office 365 beheerd door 21Vianet kunnen leren hoe ze zelfstandige Exchange Online Protection (EOP) kunnen gebruiken om hun on-premises postvakken te beschermen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4258d64721fc2042297bb15eaeecafa90dcf4bc1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929286"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>On-premises postvakken in China beveiligen met standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Dit artikel is alleen van toepassing op Office 365 beheerd door 21Vianet in China.

Zelfs als u van plan bent om een deel van uw postvakken of al uw postvakken on-premises te hosten, kunt u de postvakken nog steeds beveiligen met Exchange Online Protection (EOP). Als u verbindingslijnen wilt configureren, moet uw account een globale beheerder zijn of een exchange-bedrijfsbeheerder (de rollengroep Organisatiebeheer). Zie Beheerdersrollen [toewijzen in Office 365 beheerd door 21Vianet](../../admin/add-users/assign-admin-roles.md?preserve-view=true&view=o365-21vianet)voor informatie over de relatie tussen Office 365-machtigingen en Exchange-machtigingen. Als al uw Exchange-postvakken on-premises zijn, volgt u deze stappen om uw EOP-service in te stellen.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Stap 1: Gebruik het Microsoft 365-beheercentrum om uw domein toe te voegen en te verifiëren

1. Ga in het Microsoft 365-beheercentrum naar Setup om uw domein toe te voegen aan de service.

2. Volg de stappen in de portal om de toepasselijke DNS-records toe te voegen aan uw DNS-hostingprovider om het eigendom van het domein te verifiëren.

> [!TIP]
> Voeg uw domein en gebruikers toe aan Office 365 beheerd door [21Vianet](../../admin/setup/add-domain.md?preserve-view=true&view=o365-21vianet) en [DNS-records maken voor Office 365](../../admin/services-in-china/create-dns-records-when-you-manage-your-dns-records.md?preserve-view=true&view=o365-21vianet) wanneer u uw DNS-records beheert, zijn nuttige bronnen om naar te verwijzen terwijl u uw domein toevoegt aan de service en DNS configureert.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Stap 2: Geadresseerden toevoegen en het domeintype configureren

Voordat u uw e-mail configureert voor stroom van en naar de EOP-service, raden we u aan uw geadresseerden toe te voegen aan de service. U kunt dit op verschillende manieren doen, zoals is beschreven in [EOP e-mailgebruikers beheren.](manage-mail-users-in-eop.md) Als u dbeb (Directory Based Edge Blocking) wilt inschakelen om verificatie van geadresseerden binnen de service af te dwingen nadat u uw geadresseerden hebt toegevoegd, moet u uw domeintype instellen op Gezaghebbend. Zie Directory Based Edge Blocking gebruiken om berichten te weigeren die naar ongeldige geadresseerden [zijn verzonden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)voor meer informatie over DBEB.

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Stap 3: EAC gebruiken om e-mailstroom in te stellen

Maak verbindingslijnen in het Exchange-beheercentrum (EAC) waarmee e-mailstroom tussen EOP en uw on-premises e-mailservers kan worden ingeschakeld. Zie E-mailstroom [configureren met connectors in Office 365](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)voor gedetailleerde instructies.

 Hoe weet u dat deze taak heeft gewerkt?

 Zie [E-mailstroom testen door uw Office 365-connectors te valideren.](/exchange/mail-flow-best-practices/test-mail-flow)

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Stap 4: Binnenkomende poort 25 SMTP-toegang toestaan

Nadat u verbindingslijnen hebt geconfigureerd, wacht u 72 uur om door te geven van uw DNS-recordupdates. Beperk inkomende poort-25 SMTP-verkeer op uw firewall of e-mailservers om alleen e-mail te accepteren vanuit de EOP-datacenters, met name van de IP-adressen die worden vermeld bij URL's en [IP-adresbereiken voor Office 365.](../../enterprise/managing-office-365-endpoints.md) Dit beschermt uw on-premises omgeving door het bereik van binnenkomende berichten te beperken die u kunt ontvangen. Als u instellingen hebt op uw e-mailserver die de IP-adressen beheren die zijn toegestaan om verbinding te maken voor e-mailrelais, moet u deze instellingen ook bijwerken.

> [!TIP]
> Configureer instellingen op de SMTP-server met een verbindingstijd van 60 seconden. Deze instelling is voor de meeste situaties acceptabel, waardoor er enige vertraging kan ontstaan in het geval van een bericht dat bijvoorbeeld met een grote bijlage is verzonden.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Stap 5: Ervoor zorgen dat spam wordt doorgeleid naar de map Ongewenste e-mail van elke gebruiker

Als u ervoor wilt zorgen dat ongewenste e-mail correct wordt doorgeleid naar de map Ongewenste e-mail van elke gebruiker, moet u een paar configuratiestappen uitvoeren. De stappen worden geleverd in [Zelfstandige EOP configureren om spam te](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)verzenden naar de map Ongewenste e-mail in hybride omgevingen. Als u berichten niet naar de map Ongewenste e-mail van elke gebruiker wilt verplaatsen, kunt u een andere actie kiezen door uw antispambeleid te bewerken (ook wel bekend als beleid voor inhoudsfilters). Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Stap 6: Gebruik het Microsoft 365-beheercentrum om uw MX-record aan te wijzen op EOP

Volg de stappen voor de configuratie van het Office 365-domein om uw MX-record voor uw domein bij te werken, zodat uw binnenkomende e-mail door EOP loopt. Voor meer informatie kunt u opnieuw verwijzen naar [DNS-records maken voor Office 365 wanneer u uw DNS-records beheert.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md?preserve-view=true&view=o365-21vianet)

Hoe weet u dat deze taak heeft gewerkt?

 Zie [E-mailstroom testen door uw Office 365-connectors te valideren.](/exchange/mail-flow-best-practices/test-mail-flow)

Op dit moment hebt u de servicebezorging geverifieerd voor een correct geconfigureerde on-premises uitgaande verbindingslijn en hebt u geverifieerd dat de MX-record verwijst naar EOP. U kunt er nu voor kiezen om de volgende aanvullende tests uit te voeren om te controleren of een e-mailbericht door de service wordt bezorgd in uw on-premises omgeving:

- Klik in de Remote Connectivity Analyzer op het **tabblad Office 365** en voer vervolgens de **inkomende SMTP-e-mailtest** uit onder **Internet-e-mailtests.**

- Verzend een e-mailbericht van een web-e-mailaccount naar een e-mailontvanger in uw organisatie waarvan het domein overeenkomt met het domein dat u aan de service hebt toegevoegd. Bevestig de bezorging van het bericht in het on-premises postvak met Microsoft Outlook of een andere e-mailclient.

- Als u een uitgaande e-mailtest wilt uitvoeren, kunt u een e-mailbericht van een gebruiker in uw organisatie naar een web-e-mailaccount verzenden en bevestigen dat het bericht is ontvangen.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Minder gebruikelijk: een hybride installatie met postvakken on-premises en in de cloud

Als u exchange-postvakken on-premises hebt en een of meer postvakken in de cloud in Exchange Online, hebt u een *hybride* installatie. In een hybride installatie werken functies zoals gratis/bezet delen van agenda's en e-mailroutering samen in uw on-premises en cloudomgevingen. Mogelijk hebt u een hybride installatie ingesteld terwijl u postvakken overzet naar Exchange Online. Een hybride omgeving is anders ingesteld dan zelfstandige EOP-beveiliging.

U kunt een hybride scenario kiezen om te profiteren van e-mail in de cloud voor de meeste werknemers. U kunt dit doen terwijl u ook een aantal postvakken on-premises host; bijvoorbeeld voor uw juridische afdeling.

Een hybride installatie kan complex zijn, maar heeft veel voordelen. Zie [Hybride implementaties](/Exchange/exchange-hybrid)van Exchange Server voor meer informatie over het instellen van hybride scenario's met Exchange.