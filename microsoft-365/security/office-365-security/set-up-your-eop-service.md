---
title: De zelfstandige EOP-service instellen
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
description: Beheerders kunnen leren hoe ze zelfstandige Exchange Online Protection (EOP) kunnen instellen om on-premises e-mailomgevingen te beschermen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: de3c40a15a69eb2430c9c9b0473a983ef7c5354f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290463"
---
# <a name="set-up-your-standalone-eop-service"></a>De zelfstandige EOP-service instellen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige versie van Exchange Online Protection](exchange-online-protection-overview.md)

In dit onderwerp wordt uitgelegd hoe u zelfstandige Exchange Online Protection (EOP) kunt instellen. Als u hier terecht bent gekomen vanuit de domeinwizard van Office 365, gaat u terug naar de domeinwizard van Office 365 als u Exchange Online Protection niet wilt gebruiken. Zie E-mailstroom configureren met [connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)voor meer informatie over het configureren van connectors.

> [!NOTE]
> In dit onderwerp wordt ervan uitgenomen dat u on-premises postvakken hebt en dat u deze wilt beveiligen met EOP, dat een zelfstandig scenario wordt genoemd. Als u al uw postvakken in de cloud wilt hosten met Exchange Online, hoeft u niet alle stappen in dit artikel uit te voeren. Ga naar [Exchange Online-abonnementen vergelijken om](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) u te registreren en postvakken in de cloud aan te schaffen.
>
> Als u sommige van uw postvakken lokaal wilt hosten en sommige in de cloud, wordt dit een hybride scenario genoemd. Hiervoor zijn meer geavanceerde instellingen voor de e-mailstroom vereist. [Hybride implementaties van Exchange Server leggen](https://docs.microsoft.com/exchange/exchange-hybrid) een uitleg van de hybride e-mailstroom uit en bevat koppelingen naar bronnen die laten zien hoe u dit in kunt stellen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Geschatte tijd voor het voltooien van deze taak: 1 uur

- U moet machtigingen toegewezen krijgen in Exchange Online Protection voordat u de procedures in dit artikel kunt uitvoeren. U hebt met name de rol **Extern** en Geaccepteerd domein nodig, die standaard is toegewezen aan de rollengroepen Organisatiebeheer **(globale** beheerders) en **E-mailstroombeheerder.** Zie Machtigingen in zelfstandige EOP en gebruik het [EAC](feature-permissions-in-eop.md) om de lijst met leden [in rollengroepen te wijzigen voor meer informatie.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Als u zich nog niet hebt aangemeld voor EOP, gaat u naar [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) en kiest u ervoor om de service te kopen of uit te proberen.

- Zie Sneltoetsen voor het [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)voor informatie over sneltoetsen die van toepassing kunnen zijn op de procedures in dit artikel.

> [!TIP]
> Hebt u problemen? Vraag om hulp op het forum [van Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Stap 1: Het Microsoft 365-beheercentrum gebruiken om uw domein toe te voegen en te verifiëren

1. Ga in [het Microsoft 365-beheercentrum](../../admin/admin-overview/about-the-admin-center.md)naar **Setup** om uw domein aan de service toe te voegen.

2. Volg de stappen om de toepasselijke DNS-records toe te voegen aan uw DNS-hostingprovider om het eigendom van het domein te verifiëren.

> [!TIP]
> Voeg een domein toe aan [Office 365](../../admin/setup/add-domain.md) en maak DNS-records bij een [DNS-hostingprovider voor Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) zijn nuttige bronnen waarnaar u moet verwijzen wanneer u uw domein aan de service toevoegt en DNS configureert.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Stap 2: Geadresseerden toevoegen en desgewenst DBEB inschakelen

Voordat u uw e-mail configureert voor de stroom van en naar de EOP-service, raden we u aan uw geadresseerden aan de service toe te voegen. Er zijn verschillende manieren waarop u dit kunt doen, zoals wordt beschreven in [EOP e-mailgebruikers beheren.](manage-mail-users-in-eop.md) Als u op directory gebaseerde randblokkering (DBEB) wilt inschakelen om verificatie van geadresseerden binnen de service af te dwingen nadat u de geadresseerden hebt toegevoegd, moet u uw domeintype instellen op Gezaghebbend. Zie Op directory gebaseerde randblokkering gebruiken om berichten te weigeren die naar ongeldige geadresseerden zijn verzonden voor meer informatie over [DBEB.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Stap 3: Het EAC gebruiken om de e-mailstroom in te stellen

Maak connectors in het Exchange-beheercentrum (EAC) voor het inschakelen van de e-mailstroom tussen EOP en uw on-premises e-mailservers. Zie Connectors instellen om e-mail te routen tussen [Microsoft 365 en uw eigen e-mailservers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)voor gedetailleerde instructies.

### <a name="how-do-you-know-this-task-worked"></a>Hoe weet u of deze taak heeft gewerkt?

Controleer de e-mailstroom tussen de service en uw omgeving. Zie [E-mailstroom testen door uw Microsoft 365-connectors te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)voor meer informatie.

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Stap 4: Binnenkomende poort 25 SMTP-toegang toestaan

Nadat u connectors hebt geconfigureerd, wacht u 72 uur totdat de updates van uw DNS-records zijn doorgegeven. Hierna beperkt u het SMTP-verkeer voor binnenkomende poort 25 op uw firewall of e-mailservers tot het accepteren van e-mail alleen van de EOP-datacenters, met name van de IP-adressen die worden vermeld op IP-adressen van [Exchange Online Protection.](../../enterprise/urls-and-ip-address-ranges.md) Dit beschermt uw on-premises omgeving door het bereik van binnenkomende berichten die u kunt ontvangen te beperken. Als op uw e-mailserver instellingen zijn ingesteld voor het beheren van de IP-adressen die zijn toegestaan om verbinding te maken voor e-mailrelais, moet u deze instellingen ook bijwerken.

> [!TIP]
> Configureer instellingen op de SMTP-server met een verbindingstijd van 60 seconden. Deze instelling is in de meeste gevallen acceptabel, waardoor bijvoorbeeld enige vertraging kan ontstaan bij een bericht dat met een grote bijlage is verzonden.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Stap 5: Ervoor zorgen dat spam wordt doorvergeleid naar de map Ongewenste e-mail van elke gebruiker

Om ervoor te zorgen dat ongewenste e-mail correct wordt doorverrouteerd naar de map Ongewenste e-mail van elke gebruiker, moet u een aantal configuratiestappen uitvoeren. De stappen zijn beschikbaar in zelfstandige [EOP configureren om spam af](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)te leveren in de map Ongewenste e-mail in hybride omgevingen.

Als u geen berichten wilt verplaatsen naar de map Ongewenste e-mail van gebruikers, kunt u een andere actie kiezen door het antispambeleid te bewerken. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Stap 6: Het Microsoft 365-beheercentrum gebruiken om uw MX-record naar EOP te laten wijzen

Volg de stappen voor domeinconfiguratie om uw MX-record voor uw domein bij te werken, zodat uw binnenkomende e-mail door EOP loopt. Zorg ervoor dat u de MX-record rechtstreeks naar EOP doorverlenen in plaats van e-mail van een externe filterservice door te sturen naar EOP. Voor meer informatie kunt u opnieuw verwijzen naar [DNS-records maken voor Office 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

> [!NOTE]
> Zie [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)als u uw MX-record moet laten wijzen naar een andere server of service die voor EOP wordt geplaatst.

### <a name="how-do-you-know-this-task-worked"></a>Hoe weet u of deze taak heeft gewerkt?

U hebt nu de bezorging van de service geverifieerd voor een correct geconfigureerde uitgaande on-premises connector en u hebt geverifieerd dat de MX-record naar EOP verwijst. U kunt nu de volgende aanvullende tests uitvoeren om te controleren of een e-mailbericht door de service naar uw on-premises omgeving wordt bezorgd:

- Controleer de e-mailstroom tussen de service en uw omgeving. Zie [E-mailstroom testen door uw Microsoft 365-connectors te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)voor meer informatie.

- Verzend een e-mailbericht vanuit een web-e-mailaccount naar een e-mailgeadresseerde in uw organisatie van wie het domein overeenkomt met het domein dat u hebt toegevoegd aan de service. Bevestig de bezorging van het bericht in het on-premises postvak met Behulp van Microsoft Outlook of een andere e-mailclient.

- Als u een uitgaande e-mailtest wilt uitvoeren, kunt u een e-mailbericht van een gebruiker in uw organisatie naar een web-e-mailaccount verzenden en controleren of het bericht is ontvangen.

> [!TIP]
> Wanneer u klaar bent met de installatie, hoeft u geen extra stappen uit te voeren om ervoor te zorgen dat spam en malware door EOP worden verwijderd. EOP verwijdert spam en malware automatisch. U kunt uw instellingen echter aanpassen op basis van de behoeften van uw bedrijf. Zie Beveiliging tegen [ongewenste e-mail en malware in Office 365](anti-spam-and-anti-malware-protection.md) en Configureer spoof intelligence voor meer [informatie.](learn-about-spoof-intelligence.md)
>
> Nu uw service wordt uitgevoerd, raden we u aan aanbevolen aanbevolen procedures te lezen voor het configureren van [EOP,](best-practices-for-configuring-eop.md)waarin aanbevolen instellingen en overwegingen worden beschreven voor nadat u EOP hebt ingesteld.
