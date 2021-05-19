---
title: Uw zelfstandige EOP-service instellen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Beheerders kunnen leren hoe ze zelfstandige Exchange Online Protection (EOP) instellen om on-premises e-mailomgevingen te beveiligen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63504dd2d729674fd84eff2fd5548c8d077cd1f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538973"
---
# <a name="set-up-your-standalone-eop-service"></a>Uw zelfstandige EOP-service instellen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Exchange Online Protection zelfstandige](exchange-online-protection-overview.md)

In dit onderwerp wordt uitgelegd hoe u zelfstandige Exchange Online Protection (EOP) in te stellen. Als u hier bent geland vanuit de wizard Office 365 domeinen, gaat u terug naar de wizard Office 365 domeinen als u deze niet wilt Exchange Online Protection. Zie E-mailstroom configureren met behulp van [verbindingslijnen in](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)Office 365.

> [!NOTE]
> In dit onderwerp wordt ervan uitgenomen dat u on-premises postvakken hebt en dat u deze wilt beveiligen met EOP, wat bekend staat als een zelfstandig scenario. Als u al uw postvakken in de cloud wilt hosten met Exchange Online, hoeft u niet alle stappen in dit artikel uit te voeren. Ga naar [Vergelijken Exchange Online abonnementen om](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) u aan te melden en cloudpostvakken te kopen.
>
> Als u een deel van uw postvakken on-premises en sommige in de cloud wilt hosten, wordt dit een hybride scenario genoemd. Hiervoor zijn geavanceerdere e-mailstroominstellingen vereist. [Exchange Server hybride implementaties](/exchange/exchange-hybrid) worden hybride e-mailstroom uitgelegd en koppelingen naar resources die laten zien hoe u deze kunt instellen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Geschatte tijd om deze taak te voltooien: 1 uur

- Voordat u de procedures in dit artikel kunt uitvoeren, moet Exchange Online Protection machtigingen zijn toegewezen. U hebt met name de rol **Externe** en geaccepteerde domeinen nodig, die standaard is toegewezen aan de rollengroepen Organisatiebeheer **(globale** beheerders) en Mail **Flow Administrator.** Zie Machtigingen in zelfstandige [EOP](feature-permissions-in-eop.md) en Gebruik de EAC om de lijst met [leden in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Als u zich nog niet hebt aangemeld voor EOP, gaat u [naar](https://products.office.com/exchange/exchange-email-security-spam-protection) Exchange Online Protection en kiest u ervoor om de service te kopen of te proberen.

- Zie Sneltoetsen voor het Exchange beheercentrum in Exchange Online voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures [in dit artikel.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Hebt u problemen? Vraag om hulp in het [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Stap 1: Het beheercentrum Microsoft 365 gebruiken om uw domein toe te voegen en te verifiëren

1. Ga in [Microsoft 365 beheercentrum](../../admin/admin-overview/about-the-admin-center.md)naar **Setup** om uw domein toe te voegen aan de service.

2. Volg de stappen om de toepasselijke DNS-records toe te voegen aan uw DNS-hostingprovider om het eigendom van het domein te verifiëren.

> [!TIP]
> [Een domein toevoegen aan Office 365](../../admin/setup/add-domain.md) en DNS-records maken bij een [DNS-hostingprovider](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) voor Office 365 zijn nuttige bronnen om naar te verwijzen terwijl u uw domein toevoegt aan de service en DNS configureert.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Stap 2: Geadresseerden toevoegen en dbeb desgewenst inschakelen

Voordat u uw e-mail configureert voor stroom van en naar de EOP-service, raden we u aan uw geadresseerden toe te voegen aan de service. U kunt dit op verschillende manieren doen, zoals is beschreven in [EOP e-mailgebruikers beheren.](manage-mail-users-in-eop.md) Als u dbeb (Directory Based Edge Blocking) wilt inschakelen om verificatie van geadresseerden binnen de service af te dwingen nadat u uw geadresseerden hebt toegevoegd, moet u uw domeintype instellen op Gezaghebbend. Zie Directory Based Edge Blocking gebruiken om berichten te weigeren die naar ongeldige geadresseerden [zijn verzonden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)voor meer informatie over DBEB.

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Stap 3: EAC gebruiken om e-mailstroom in te stellen

Maak verbindingslijnen in het Exchange-beheercentrum (EAC) waarmee e-mailstroom tussen EOP en uw on-premises e-mailservers kan worden ingeschakeld. Zie Connectors instellen om e-mail tussen e-mail te Microsoft 365 en uw [eigen e-mailservers](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)voor gedetailleerde instructies.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

Controleer de e-mailstroom tussen de service en uw omgeving. Zie E-mailstroom testen door [uw verbindingslijnen Microsoft 365 valideren voor meer informatie.](/exchange/mail-flow-best-practices/test-mail-flow)

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Stap 4: Binnenkomende poort 25 SMTP-toegang toestaan

Nadat u verbindingslijnen hebt geconfigureerd, wacht u 72 uur om door te geven van uw DNS-recordupdates. Beperk hierna binnenkomende poort-25 SMTP-verkeer op uw firewall of e-mailservers om alleen e-mail te accepteren vanuit de EOP-datacenters, met name van de IP-adressen die worden vermeld op [Exchange Online Protection IP-adressen.](../../enterprise/urls-and-ip-address-ranges.md) Dit beschermt uw on-premises omgeving door het bereik van binnenkomende berichten te beperken die u kunt ontvangen. Als u instellingen hebt op uw e-mailserver die de IP-adressen beheren die zijn toegestaan om verbinding te maken voor e-mailrelais, moet u deze instellingen ook bijwerken.

> [!TIP]
> Configureer instellingen op de SMTP-server met een verbindingstijd van 60 seconden. Deze instelling is voor de meeste situaties acceptabel, waardoor er enige vertraging kan ontstaan in het geval van een bericht dat bijvoorbeeld met een grote bijlage is verzonden.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Stap 5: Ervoor zorgen dat spam wordt doorgeleid naar de map Ongewenste e-mail van elke gebruiker

Als u ervoor wilt zorgen dat ongewenste e-mail correct wordt doorgeleid naar de map Ongewenste e-mail van elke gebruiker, moet u een paar configuratiestappen uitvoeren. De stappen worden geleverd in [Zelfstandige EOP configureren om spam te](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)verzenden naar de map Ongewenste e-mail in hybride omgevingen.

Als u berichten niet naar de map Ongewenste e-mail van elke gebruiker wilt verplaatsen, kunt u een andere actie kiezen door uw antispambeleid te bewerken. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Stap 6: Gebruik het Microsoft 365 beheercentrum om uw MX-record aan te wijzen op EOP

Volg de stappen voor domeinconfiguratie om uw MX-record voor uw domein bij te werken, zodat uw binnenkomende e-mail door EOP loopt. Zorg ervoor dat u uw MX-record rechtstreeks naar EOP wijs, in plaats van dat een filterservice van derden e-mail doorslaaft naar EOP. Voor meer informatie kunt u opnieuw verwijzen naar [DNS-records maken voor Office 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

> [!NOTE]
> Zie Verbeterde filtering voor [connectors in](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)Exchange Online als u de MX-record naar een andere server of service moet wijzen die zich voor EOP bevindt.

### <a name="how-do-you-know-this-task-worked"></a>Hoe weet u dat deze taak heeft gewerkt?

Op dit moment hebt u de servicebezorging geverifieerd voor een correct geconfigureerde on-premises uitgaande verbindingslijn en hebt u geverifieerd dat de MX-record verwijst naar EOP. U kunt er nu voor kiezen om de volgende aanvullende tests uit te voeren om te controleren of een e-mailbericht door de service wordt bezorgd in uw on-premises omgeving:

- Controleer de e-mailstroom tussen de service en uw omgeving. Zie E-mailstroom testen door [uw verbindingslijnen Microsoft 365 valideren voor meer informatie.](/exchange/mail-flow-best-practices/test-mail-flow)

- Verzend een e-mailbericht van een web-e-mailaccount naar een e-mailontvanger in uw organisatie waarvan het domein overeenkomt met het domein dat u aan de service hebt toegevoegd. Bevestig de bezorging van het bericht in het on-premises postvak met Behulp van Microsoft Outlook of een andere e-mailclient.

- Als u een uitgaande e-mailtest wilt uitvoeren, kunt u een e-mailbericht van een gebruiker in uw organisatie naar een web-e-mailaccount verzenden en bevestigen dat het bericht is ontvangen.

> [!TIP]
> Wanneer u de installatie hebt voltooid, hoeft u geen extra stappen uit te voeren om ervoor te zorgen dat EOP spam en malware verwijdert. EOP verwijdert automatisch spam en malware. U kunt uw instellingen echter aanpassen op basis van uw bedrijfsvereisten. Zie Bescherming tegen spam en [anti-malware in EOP](anti-spam-and-anti-malware-protection.md) en [Anti-phishingbeveiliging in](anti-phishing-protection.md)Microsoft 365.
>
> Nu uw service wordt uitgevoerd, raden we u aan Aanbevolen procedures te lezen voor het configureren van [EOP,](best-practices-for-configuring-eop.md)waarin aanbevolen instellingen en aandachtspunten worden beschreven voor nadat u EOP hebt ingesteld.