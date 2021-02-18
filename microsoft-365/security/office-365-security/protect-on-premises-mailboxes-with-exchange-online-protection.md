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
description: Beheerders in China die Office 365 gebruiken en worden beheerd door 21Vianet, kunnen leren hoe ze zelfstandige Exchange Online Protection (EOP) kunnen gebruiken om hun on-premises postvakken te beschermen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f4f27fa9237d76422e936555c9872b83655d7b6b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289423"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>On-premises postvakken in China beveiligen met standalone EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Dit artikel geldt alleen voor Office 365 beheerd door 21Vianet in China.

Zelfs als u van plan bent om sommige of alle postvakken on-premises te hosten, kunt u de postvakken nog steeds beveiligen met Exchange Online Protection (EOP). Als u connectors wilt configureren, moet uw account een globale beheerder of een beheerder van een Exchange-bedrijf (de rollengroep Organisatiebeheer) zijn. Zie Beheerdersrollen toewijzen in Office 365 beheerd door 21Vianet voor informatie over de relatie tussen Office [365-machtigingen en Exchange-machtigingen.](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet&preserve-view=true) Als al uw Exchange-postvakken on-premises zijn, volgt u deze stappen om uw EOP-service in te stellen.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Stap 1: Het Microsoft 365-beheercentrum gebruiken om uw domein toe te voegen en te verifiëren

1. Navigeer in het Microsoft 365-beheercentrum naar Setup om uw domein aan de service toe te voegen.

2. Volg de stappen in de portal om de toepasselijke DNS-records toe te voegen aan uw DNS-hostingprovider om het eigendom van het domein te verifiëren.

> [!TIP]
> Voeg uw domein en gebruikers toe aan Office 365 beheerd door [21Vianet](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet&preserve-view=true) en MAAK [DNS-records voor Office 365](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet&preserve-view=true) wanneer u uw DNS-records beheert, zijn nuttige bronnen waarnaar u moet verwijzen wanneer u uw domein aan de service toevoegt en DNS configureert.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Stap 2: Geadresseerden toevoegen en het domeintype configureren

Voordat u uw e-mail configureert voor de stroom van en naar de EOP-service, raden we u aan uw geadresseerden aan de service toe te voegen. Er zijn verschillende manieren waarop u dit kunt doen, zoals wordt beschreven in [EOP e-mailgebruikers beheren.](manage-mail-users-in-eop.md) Als u op directory gebaseerde randblokkering (DBEB) wilt inschakelen om verificatie van geadresseerden binnen de service af te dwingen nadat u de geadresseerden hebt toegevoegd, moet u uw domeintype instellen op Gezaghebbend. Zie Op directory gebaseerde randblokkering gebruiken om berichten te weigeren die naar ongeldige geadresseerden zijn verzonden voor meer informatie over [DBEB.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Stap 3: Het EAC gebruiken om de e-mailstroom in te stellen

Maak connectors in het Exchange-beheercentrum (EAC) voor het inschakelen van de e-mailstroom tussen EOP en uw on-premises e-mailservers. Zie [E-mailstroom configureren met connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)voor gedetailleerde instructies.

 Hoe weet u of deze taak heeft gewerkt?

 Zie [E-mailstroom testen door uw Office 365-connectors te valideren.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Stap 4: Binnenkomende poort 25 SMTP-toegang toestaan

Nadat u connectors hebt geconfigureerd, wacht u 72 uur totdat de updates van uw DNS-records zijn doorgegeven. Hierna beperkt u het SMTP-verkeer voor binnenkomende poort 25 op uw firewall of e-mailservers tot het accepteren van e-mail alleen van de EOP-datacenters, met name van de IP-adressen die worden vermeld in URL's en IP-adresbereiken voor [Office 365.](../../enterprise/managing-office-365-endpoints.md) Dit beschermt uw on-premises omgeving door het bereik van binnenkomende berichten die u kunt ontvangen te beperken. Als op uw e-mailserver instellingen zijn ingesteld voor het beheren van de IP-adressen die zijn toegestaan om verbinding te maken voor e-mailrelais, moet u deze instellingen ook bijwerken.

> [!TIP]
> Configureer instellingen op de SMTP-server met een verbindingstijd van 60 seconden. Deze instelling is in de meeste gevallen acceptabel, waardoor bijvoorbeeld enige vertraging kan ontstaan wanneer een bericht met een grote bijlage wordt verzonden.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Stap 5: Ervoor zorgen dat spam wordt doorvergeleid naar de map Ongewenste e-mail van elke gebruiker

U moet een aantal configuratiestappen uitvoeren om ervoor te zorgen dat ongewenste e-mail correct wordt doorverrouteerd naar de map Ongewenste e-mail van elke gebruiker. De stappen zijn beschikbaar in zelfstandige [EOP configureren om spam af](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)te leveren in de map Ongewenste e-mail in hybride omgevingen. Als u geen berichten wilt verplaatsen naar de map Ongewenste e-mail van elke gebruiker, kunt u een andere actie kiezen door het antispambeleid (ook wel inhoudsfilterbeleid genoemd) te bewerken. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Stap 6: Het Microsoft 365-beheercentrum gebruiken om uw MX-record naar EOP te laten wijzen

Volg de configuratiestappen voor het Office 365-domein om uw MX-record voor uw domein bij te werken, zodat uw binnenkomende e-mail door EOP loopt. Voor meer informatie kunt u opnieuw verwijzen naar [DNS-records voor Office 365 maken wanneer u uw DNS-records beheert.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-21vianet&preserve-view=true)

Hoe weet u of deze taak heeft gewerkt?

 Zie [E-mailstroom testen door uw Office 365-connectors te valideren.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

U hebt nu de bezorging van de service geverifieerd voor een correct geconfigureerde uitgaande on-premises connector en u hebt geverifieerd dat de MX-record naar EOP verwijst. U kunt nu de volgende aanvullende tests uitvoeren om te controleren of een e-mailbericht door de service naar uw on-premises omgeving wordt bezorgd:

- Klik in Remote Connectivity Analyzer op het tabblad **Office 365** en voer vervolgens de test van binnenkomende **SMTP-e-mail** uit onder **Internet-e-mailtests.**

- Verzend een e-mailbericht vanuit een web-e-mailaccount naar een e-mailgeadresseerde in uw organisatie van wie het domein overeenkomt met het domein dat u hebt toegevoegd aan de service. Bevestig de bezorging van het bericht in het on-premises postvak met Behulp van Microsoft Outlook of een andere e-mailclient.

- Als u een uitgaande e-mailtest wilt uitvoeren, kunt u een e-mailbericht van een gebruiker in uw organisatie naar een web-e-mailaccount verzenden en controleren of het bericht is ontvangen.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Minder algemeen: een hybride installatie met on-premises postvakken en in de cloud

Als u on-premises Exchange-postvakken hebt en een of meer postvakken in de cloud in Exchange Online, hebt u een *hybride* installatie. In een hybride installatie werken functies zoals het delen van agenda's met bezet en e-mailroutering samen in uw on-premises omgevingen en in de cloud. Mogelijk is er een hybride installatie ingesteld terwijl u postvakken overzet naar Exchange Online. Een hybride omgeving is anders ingesteld dan zelfstandige bescherming van EOP.

U kunt een hybride scenario kiezen om gebruik te maken van cloud-e-mail voor de meeste werknemers. U kunt dit doen terwijl u ook sommige postvakken on-premises host. bijvoorbeeld voor uw juridische afdeling.

Een hybride installatie kan complex zijn, maar dit heeft vele voordelen. Zie hybride implementaties van Exchange Server voor meer informatie over het instellen van hybride [scenario's met Exchange.](https://docs.microsoft.com/Exchange/exchange-hybrid)
