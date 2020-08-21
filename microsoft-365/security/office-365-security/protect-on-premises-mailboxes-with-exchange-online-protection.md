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
description: Beheerders in China met Office 365, beheerd door 21Vianet, kunnen informatie over het gebruik van zelfstandige Exchange Online Protection (EOP) om hun on-premises postvakken te beschermen.
ms.openlocfilehash: 57b9e7519edf92438662ecbf27c93b662d9e8f71
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826811"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>On-premises postvakken in China beveiligen met standalone EOP

> [!NOTE]
> Dit artikel is alleen van toepassing op Office 365, dat wordt beheerd door 21Vianet in China.

Zelfs als u van plan bent om sommige of alle postvakken on-premises te hosten, kunt u de postvakken nog steeds beschermen met Exchange Online Protection (EOP). Voor het configureren van connectors moet uw account een globale beheerder of een beheerder van Exchange-beheerder (de rollen groep Organisatiebeheer) zijn. Zie [beheerdersrollen toewijzen in Office 365 beheerd door 21vianet](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet)voor informatie over de machtigingen van Office 365 met betrekking tot Exchange-machtigingen. Als al uw Exchange-postvakken on-premises zijn, voert u deze stappen uit om de EOP-service in te stellen.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Stap 1: het Microsoft 365-Beheercentrum gebruiken om uw domein toe te voegen en te verifiëren

1. Ga in het Microsoft 365-Beheercentrum naar instellingen om uw domein aan de service toe te voegen.

2. Volg de stappen in de portal om de toepasselijke DNS-records toe te voegen aan uw DNS-hosting provider om de eigendom van het domein te verifiëren.

> [!TIP]
> [Uw domein en gebruikers toevoegen aan Office 365, beheerd door 21vianet](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet) en [DNS-records voor Office 365 maken wanneer u uw DNS-records beheert](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet) , zijn nuttige bronnen voor verwijzingen wanneer u uw domein aan de service toevoegt en DNS configureert.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Stap 2: geadresseerden toevoegen en het domeintype configureren

Voordat u uw e-mailberichten configureert en van de EOP-service configureert, wordt u aangeraden de geadresseerden toe te voegen aan de service. U kunt dit op verschillende manieren doen, zoals beschreven in [e-mail gebruikers beheren in EOP](manage-mail-users-in-eop.md). Als u wilt toestaan dat er op mappen gebaseerde Edge blocking (DBEB) wordt gebruikt om de verificatie van de ontvanger binnen de service af te dwingen nadat u de geadresseerden hebt toegevoegd, moet u uw domeintype instellen op gezaghebbend. Zie voor meer informatie over DBEB voor meer informatie over [het gebruik van op mappen gebaseerde blokken blokkeren om berichten die naar ongeldige geadresseerden zijn verzonden, af te](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)wijzen.

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Stap 3: het Exchange-Beheercentrum gebruiken voor het instellen van de e-mail stroom

Maak verbindingslijnen in het Exchange-Beheercentrum waarmee u de e-mail stroom tussen EOP en uw on-premises e-mailservers kunt inschakelen. Zie [e-mail stroom configureren met connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)voor gedetailleerde instructies.

 Hoe weet u of deze taak heeft gewerkt?

 Zie [e-mail stroom testen door uw Office 365-connectors te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Stap 4: binnenkomende poort 25 SMTP-toegang toestaan

Nadat u de connectors hebt geconfigureerd, wacht u 72 uur om doorgifte van uw DNS-record updates toe te staan. Daarom moet u de binnenkomende poorten van het SMTP-e-mailbericht op uw firewall of e-mailservers beperken, zodat u alleen e-mail kunt ontvangen van de EOP-datacenters, specifiek van de IP-adressen die worden vermeld bij [url's en IP-adresbereiken voor Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints). Hiermee beschermt u uw on-premises omgeving door het bereik van inkomende inkomende berichten te beperken. Als u de instellingen op uw e-mailserver hebt die bepalen welke IP-adressen verbinding kunnen maken voor e-mail relay, moet u deze instellingen ook bijwerken.

> [!TIP]
> Configureer de instellingen op de SMTP-server met een verbindingstijd van 60 seconden. Deze instelling is toegestaan voor de meeste situaties, zodat u wat vertraging in het geval van een bericht met een grote bijlage kunt verzenden.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Stap 5: ervoor zorgen dat spam wordt gerouteerd naar de map Ongewenste E-mail van elke gebruiker

U moet een paar configuratiestappen uitvoeren om ervoor te zorgen dat spam (ongewenste e-mail) correct wordt gerouteerd naar de map Ongewenste E-mail in elke gebruiker. U vindt de stappen in [zelfstandige EOP configureren voor spam op de map Ongewenste e-mail in hybride omgevingen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Als u berichten niet naar de map Ongewenste E-mail van de gebruiker wilt verplaatsen, kunt u een andere actie kiezen door uw Antispambeleid te bewerken (ook wel inhouds filter beleid genoemd). Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Stap 6: het Microsoft 365-Beheercentrum gebruiken om uw MX-record te laten verwijzen naar EOP

Volg de configuratiestappen van Office 365 Domain om uw MX-record voor uw domein bij te werken, zodat de inkomende e-mail wordt doorgevoerd via EOP. [Als u de DNS-records beheert, kunt u meer informatie raadplegen over het maken van DNS-records voor Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Hoe weet u of deze taak heeft gewerkt?

 Zie [e-mail stroom testen door uw Office 365-connectors te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

Op dit moment hebt u de service levering voor een correct geconfigureerde, uitgaande on-premises connector gecontroleerd en u hebt gecontroleerd of uw MX-record de EOP wijst. U kunt nu de volgende extra testen uitvoeren om te controleren of een e-mailbericht door de service naar uw on-premises omgeving wordt verzonden:

- Ga in de Remote Connectivity Analyzer naar het tabblad **Office 365** en voer de test **inkomende SMTP-e-mail** onder **Internet-e-mail tests**uit.

- Een e-mailbericht verzenden vanuit een e-mailaccount op het web naar een e-mailadres in uw organisatie waarvan het domein overeenkomt met het domein dat u hebt toegevoegd aan de service. Bevestig de bezorging van het bericht in het on-premises postvak via Microsoft Outlook of een ander e-mailclient.

- Als u een uitgaande e-mail test wilt uitvoeren, kunt u een e-mailbericht van een gebruiker in uw organisatie verzenden naar een e-mailaccount op het web en controleren of het bericht is ontvangen.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Minder algemeen: een hybride installatie met zowel on-premises postvakken als postvakken in de Cloud

Als u Exchange-postvakken on-premises en een of meer postvakken in de cloud in Exchange Online hebt, hebt u een *hybride* installatie. In een hybride configuratie werken functies zoals beschikbaarheids delen van agenda en e-mail routering samen in uw on-premises omgevingen en Cloud omgevingen. U hebt mogelijk een hybride installatie, terwijl u overstapt op postvakken naar Exchange Online. Een hybride omgeving is anders ingesteld dan EOP zelfstandige beveiliging.

U kunt een hybride scenario kiezen om te profiteren van de Cloud-e-mail voor de meeste werknemers. U kunt dit doen wanneer u ook on-premises postvakken host. voor uw wettelijke afdeling.

Een hybride installatie kan complex zijn, maar biedt een groot aantal voordelen. Als u meer wilt weten over het instellen van hybride scenario's met Exchange, raadpleegt u [hybride implementaties van Exchange Server](https://docs.microsoft.com/Exchange/exchange-hybrid).
