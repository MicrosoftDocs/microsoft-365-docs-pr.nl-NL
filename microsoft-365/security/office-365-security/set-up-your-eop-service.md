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
ms.service: O365-seccomp
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Beheerders kunnen informatie lezen over het instellen van zelfstandige Exchange Online Protection (EOP) om on-premises e-mail omgevingen te beschermen.
ms.openlocfilehash: e6ca3965dd82bf0e6ed7e361984758ab34e3eea0
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307589"
---
# <a name="set-up-your-standalone-eop-service"></a>Uw zelfstandige EOP-service instellen

In dit onderwerp wordt uitgelegd hoe u zelfstandige Exchange Online Protection (EOP) kunt instellen. Als u hier de wizard Office 365 domains hebt gezet, gaat u terug naar de wizard domeinen van Office 365 als u Exchange Online Protection niet wilt gebruiken. Zie [e-mail stroom configureren met connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)als u meer informatie zoekt over het configureren van connectors.

> [!NOTE]
> In dit onderwerp wordt ervan uitgegaan dat u on-premises postvakken hebt en u deze wilt beschermen met EOP, een zogenaamde standalone scenario. Als u al uw postvakken in de Cloud wilt hosten met Exchange Online, hoeft u niet alle stappen in dit artikel uit te voeren. Ga naar [Exchange Online-abonnementen vergelijken](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) om u aan te melden en de Cloud postvakken te kopen. Als u bepaalde postvakken on-premises wilt hosten en bepaalde in de Cloud, wordt dit ook wel een hybride scenario genoemd. Voor de toepassing zijn meer geavanceerde instellingen voor e-mail stroom nodig. [Hybride implementaties van Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid) legt een hybride e-mail stroom in en bevat koppelingen naar bronnen waarin wordt getoond hoe u deze kunt instellen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Geschatte tijd voor het voltooien van deze taak: 1 uur

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Specifiek hebt u de rol van extern en geaccepteerde domeinen nodig die standaard is toegewezen aan de rollen groepen MailFlowAdministrator en de organizationmanagement (globale beheerders). Zie voor meer informatie [machtigingen in zelfstandige EOP](feature-permissions-in-eop.md) en [Gebruik de lijst met wijzigingen in de lijst met leden van rollen groepen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Als u zich nog niet hebt geregistreerd voor EOP, gaat u naar [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) en kiest u of u de service wilt kopen of uitproberen.

- Zie toetscombinaties [voor het Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)voor informatie over toetscombinaties die van toepassing kunnen zijn op de procedures in dit onderwerp.

> [!TIP]
> Problemen? Vraag om hulp op het forum van [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Stap 1: het Microsoft 365-Beheercentrum gebruiken om uw domein toe te voegen en te verifiëren

1. Ga in het [Microsoft 365-Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/admin-overview/about-the-admin-center)naar **Setup** om uw domein aan de service toe te voegen.

2. Voer de stappen uit om de toepasselijke DNS-records toe te voegen aan uw DNS-hosting provider om de eigendom van het domein te verifiëren.

> [!TIP]
> [Een domein toevoegen aan Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) en [DNS-records maken bij een DNS-hosting provider voor Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) zijn nuttige bronnen waarnaar wordt verwezen wanneer u uw domein aan de service toevoegt en DNS configureert.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Stap 2: geadresseerden toevoegen en desgewenst DBEB inschakelen

Voordat u uw e-mailberichten configureert en van de EOP-service configureert, wordt u aangeraden de geadresseerden toe te voegen aan de service. U kunt dit op verschillende manieren doen, zoals beschreven in [e-mail gebruikers beheren in EOP](manage-mail-users-in-eop.md). Als u wilt toestaan dat er op mappen gebaseerde Edge blocking (DBEB) wordt gebruikt om de verificatie van de ontvanger binnen de service af te dwingen nadat u de geadresseerden hebt toegevoegd, moet u uw domeintype instellen op gezaghebbend. Zie voor meer informatie over DBEB voor meer informatie over [het gebruik van op mappen gebaseerde blokken blokkeren om berichten die naar ongeldige geadresseerden zijn verzonden, af te](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)wijzen.

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Stap 3: het Exchange-Beheercentrum gebruiken voor het instellen van de e-mail stroom

Maak verbindingslijnen in het Exchange-Beheercentrum waarmee u de e-mail stroom tussen EOP en uw on-premises e-mailservers kunt inschakelen. Zie [connectors instellen voor het routeren van e-mail tussen Microsoft 365 en uw eigen e-mailservers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)voor uitgebreide instructies.

### <a name="how-do-you-know-this-task-worked"></a>Hoe weet u of deze taak heeft gewerkt?

Controleer de e-mail stroom tussen de service en uw omgeving. Zie voor meer informatie [e-mail stroom testen door uw Microsoft 365-connectors te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Stap 4: binnenkomende poort 25 SMTP-toegang toestaan

Nadat u de connectors hebt geconfigureerd, wacht u 72 uur om het doorsturen van uw DNS-record toe te staan. Daarom beperkt u de inkomende e-mail van het SMTP-e-mailprogramma op uw firewall of e-mailservers, zodat alleen e-mail wordt ontvangen van de EOP-datacenters, specifiek van de IP-adressen die worden vermeld op [IP-adressen van Exchange Online Protection](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges). Hiermee beschermt u uw on-premises omgeving door het bereik van inkomende inkomende berichten te beperken. Als u de instellingen op uw e-mailserver hebt die bepalen welke IP-adressen verbinding kunnen maken voor e-mail relay, moet u deze instellingen ook bijwerken.

> [!TIP]
> Configureer de instellingen op de SMTP-server met een verbindingstijd van 60 seconden. Deze instelling is toegestaan voor de meeste situaties, zodat u wat vertraging in het geval van een bericht met een grote bijlage kunt verzenden.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Stap 5: ervoor zorgen dat spam wordt gerouteerd naar de map Ongewenste E-mail van elke gebruiker

U moet een paar configuratiestappen uitvoeren om ervoor te zorgen dat spam (ongewenste e-mail) correct wordt gerouteerd naar de map Ongewenste E-mail in elke gebruiker. U vindt de stappen in [zelfstandige EOP configureren voor spam op de map Ongewenste e-mail in hybride omgevingen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

Als u berichten niet naar de map Ongewenste E-mail van de gebruiker wilt verplaatsen, kunt u een andere actie kiezen door uw Antispambeleid te bewerken. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Stap 6: het Microsoft 365-Beheercentrum gebruiken om uw MX-record te laten verwijzen naar EOP

Volg de stappen voor het configureren van de domeinconfiguratie om uw MX-record voor uw domein bij te werken, zodat de inkomende e-mail doorloopt via EOP. Zorg ervoor dat u uw MX-record rechtstreeks aanwijst naar EOP, in plaats van een e-mailbericht van een derde persoon om te filteren, doorsturen naar EOP. Als u meer informatie wilt, kunt u opnieuw naar [DNS-records maken voor Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

> [!NOTE]
> Als u uw MX-record moet verwijzen naar een andere server of service die zich voor EOP bevindt, raadpleegt u [verbeterde filters voor verbindingslijnen in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

### <a name="how-do-you-know-this-task-worked"></a>Hoe weet u of deze taak heeft gewerkt?

Op dit moment hebt u de service levering voor een correct geconfigureerde, uitgaande on-premises connector gecontroleerd en u hebt gecontroleerd of uw MX-record de EOP wijst. U kunt nu de volgende extra testen uitvoeren om te controleren of een e-mailbericht door de service naar uw on-premises omgeving wordt verzonden:

- Controleer de e-mail stroom tussen de service en uw omgeving. Zie voor meer informatie [e-mail stroom testen door uw Microsoft 365-connectors te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

- Een e-mailbericht verzenden vanuit een e-mailaccount op het web naar een e-mailadres in uw organisatie waarvan het domein overeenkomt met het domein dat u hebt toegevoegd aan de service. Bevestig de bezorging van het bericht in het on-premises postvak via Microsoft Outlook of een ander e-mailclient.

- Als u een uitgaande e-mail test wilt uitvoeren, kunt u een e-mailbericht van een gebruiker in uw organisatie verzenden naar een e-mailaccount op het web en controleren of het bericht is ontvangen.

> [!TIP]
> Wanneer u klaar bent met de installatie, hoeft u geen extra stappen uit te voeren om te zorgen dat EOP spam en malware verwijdert. EOP verwijdert spam en malware automatisch. U kunt echter uw instellingen verfijnen op basis van uw bedrijfsvereisten. Zie [antispam en beveiliging tegen malware in Office 365](anti-spam-and-anti-malware-protection.md) en [vervalsings informatie configureren](learn-about-spoof-intelligence.md)voor meer informatie. <br/><br/> Nu uw service wordt uitgevoerd, adviseren we [Best practices voor het configureren van EOP](best-practices-for-configuring-eop.md), waarin aanbevolen instellingen en overwegingen worden beschreven voor het instellen van EOP.
