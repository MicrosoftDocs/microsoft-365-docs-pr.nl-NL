---
title: Mail flow Intelligence
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Beheerders kunnen de foutcodes voor de bezorging van berichten achterhalen via connectors (ook wel e-mail stroom informatie genoemd).
ms.openlocfilehash: e8427f3e0341ccb381121b6cdc83d20727713d4c
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307915"
---
# <a name="mail-flow-intelligence-in-eop"></a>E-mailstroomanalyse in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken gebruikt u meestal een verbindingslijn voor het routeren van e-mailberichten van EOP naar uw on-premises e-mail omgeving. U kunt ook een connector gebruiken om berichten van Microsoft 365 door te sturen naar een partnerorganisatie. Wanneer Microsoft 365 deze berichten niet via de connector bezorgt, worden deze in de wachtrij geplaatst in Microsoft 365. Microsoft 365 blijft gedurende 24 uur opnieuw proberen voor elk bericht. Na 24 uur verloopt het bericht in de wachtrij en wordt het verzonden naar de oorspronkelijke afzender in een rapport over niet-uitgevoerde bezorging (ook wel een NDR genoemd of een bericht met een stuiter bericht).

In Microsoft 365 wordt een fout gegenereerd wanneer een bericht niet kan worden afgeleverd via een verbindingslijn. In dit onderwerp worden de meest voorkomende fouten en hun oplossingen beschreven. Gezamenlijk, Queuing-en meldings fouten voor niet-bezorg bare berichten die via connectors worden verzonden, worden ook wel _e-mail stroom informatie_genoemd.

## <a name="error-code-450-44312-dns-query-failed"></a>Foutcode: 450 4.4.312 DNS-query mislukt

Deze fout betekent meestal dat Microsoft 365 probeert verbinding te maken met de Smart host die is opgegeven in de connector, maar de DNS-query voor het zoeken van de IP-adressen van de Smart host is mislukt. De mogelijke oorzaken van deze fout zijn:

- Er is een probleem met de DNS-hostingservice van uw domein (de partij die de gezaghebbende naamservers voor uw domein beheert).

- Uw domein is onlangs verlopen, zodat de MX-record niet kan worden opgehaald.

- De MX-record van uw domein is onlangs gewijzigd en de DNS-servers hebben nog steeds eerder DNS-gegevens in de cache voor uw domein.

### <a name="how-do-i-fix-error-code-450-44312"></a>Hoe los ik foutcode 450 4.4.312?

- Werk samen met uw DNS-hostingservice om het probleem met uw domein op te sporen en op te lossen.

- Neem contact op met uw partner om dit probleem op te lossen als de fout zich bevindt in uw partnerorganisatie (bijvoorbeeld een derde Cloud serviceprovider).

## <a name="error-code-450-44315-connection-timed-out"></a>Foutcode: 4.4.315-verbinding voor 450 is verlopen

Dit betekent meestal dat Microsoft 365 geen verbinding kan maken met de doel-e-mailserver. Het probleem wordt uitgelegd met de foutgegevens. Bijvoorbeeld:

- Uw on-premises e-mailserver is niet beschikbaar.

- Er is een fout opgetreden in de instellingen van de Smart host van de connector, dus Microsoft 365 probeert verbinding te maken met het verkeerde IP-adres.

### <a name="how-do-i-fix-error-code-450-44315"></a>Hoe los ik foutcode 450 4.4.315?

- Kijk welke scenario op u van toepassing is en breng de benodigde wijzigingen aan. Als de e-mail stroom bijvoorbeeld goed werkte en u de instellingen voor de connector niet hebt gewijzigd, moet u uw on-premises e-mail omgeving controleren om te zien of de server offline is, of dat er wijzigingen zijn aangebracht in de netwerkinfrastructuur, zodat u nu verschillende IP-adressen hebt gewijzigd.

- Neem contact op met uw partner om dit probleem op te lossen als de fout zich bevindt in uw partnerorganisatie (bijvoorbeeld een derde Cloud serviceprovider).

## <a name="error-code-450-44316-connection-refused"></a>Foutcode: 450 4.4.316 verbinding geweigerd

Dit betekent meestal dat er in Microsoft 365 een verbindingsfout is opgetreden bij het proberen verbinding te maken met de doel-e-mailserver. Deze fout is waarschijnlijk veroorzaakt doordat de firewall verbindingen van Microsoft 365 IP-adressen blokkeert. Of de fout kan door ontwerp zijn als u uw on-premises e-mailsysteem volledig hebt gemigreerd naar Microsoft 365 en uw on-premises e-mail omgeving afsluit.

### <a name="how-do-i-fix-error-code-450-44316"></a>Hoe los ik foutcode 450 4.4.316?

- Als u postvakken hebt in uw on-premises omgeving, moet u de firewallinstellingen wijzigen om verbindingen van Microsoft 365 IP-adressen op TCP-poort 25 toe te staan voor uw on-premises e-mailservers. Zie [url's en IP-adresbereiken voor Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)voor een lijst met de microsoft 365 IP-adressen.

- Als u geen berichten meer wilt ontvangen in uw on-premises omgeving, klikt u op **nu herstellen** in de melding zodat microsoft 365 de berichten met ongeldige geadresseerden direct kan afwijzen. Hierdoor wordt het risico voor het overschrijden van het quotum van de organisatie voor ongeldige geadresseerden verminderd, wat van invloed kan zijn op de bezorging van normaal berichten. U kunt ook de volgende instructies gebruiken om het probleem handmatig op te lossen:

  - In het [Exchange-Beheercentrum](https://docs.microsoft.com/Exchange/exchange-admin-center), schakelt u de connector voor E-mail van microsoft 365 in de on-premises e-mail omgeving uit of verwijdert u deze.

    1. Ga in het Exchange-Beheercentrum naar **e-mail stroom** \> **verbindingslijnen**.

    2. Selecteer de connector met de **From** waarde van **Office 365** en de waarde **voor** de **e-mailserver van uw organisatie** en voer een van de volgende stappen uit:

       - Als u de verbindingslijn wilt verwijderen **, klikt u** op het ![ pictogram verwijderen](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Schakel de verbindingslijn uit **Edit** door te klikken op het ![ pictogram bewerken bewerken ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) en **het**selectievakje in te schakelen.

  - Wijzig het geaccepteerde domein in Microsoft 365 dat is gekoppeld aan uw on-premises e-mail omgeving van **interne** doorgifte naar **gezaghebbend**. Zie [geaccepteerde domeinen beheren in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)voor instructies.

  **Opmerking**: deze wijzigingen treden doorgaans tussen 30 minuten en één uur in werking. Na één uur controleert u of u de fout niet meer ontvangt.

- Neem contact op met uw partner om dit probleem op te lossen als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudservice provider).

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Foutcode: 450 4.4.317 kan geen verbinding maken met de externe server

Dit betekent meestal dat Microsoft 365 is verbonden met de doel-e-mailserver, maar de server heeft gereageerd met een onmiddellijke fout of niet aan de verbindings vereisten voldoet. Het probleem wordt uitgelegd met de foutgegevens. Bijvoorbeeld:

- De doel-e-mailserver heeft gereageerd op de fout ' service niet beschikbaar ', wat aangeeft dat de server geen communicatie kan bijhouden met Microsoft 365.

- De connector is geconfigureerd om TLS te vereisen, maar de doel-e-mailserver biedt geen ondersteuning voor TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Hoe los ik foutcode 450 4.4.317?

- Controleer de TLS-instellingen en certificaten op uw on-premises e-mailservers en de TLS-instellingen op de connector.

- Neem contact op met uw partner om dit probleem op te lossen als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudservice provider).

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Foutcode: 450-verbinding voor 4.4.318 is plotseling gesloten

Deze fout betekent meestal dat Microsoft 365 geen problemen ondervindt met de on-premises e-mail omgeving, zodat de verbinding is verbroken. De mogelijke oorzaken van deze fout zijn:

- De firewall gebruikt regels voor SMTP-pakket onderzoek en deze regels werken niet goed.

- Uw on-premises e-mailserver werkt niet goed (bijvoorbeeld de service loopt vast, loopt vast of onvoldoende systeembronnen), waardoor de server een time-out heeft en sluit de verbinding met Microsoft 365.

- Er zijn netwerkproblemen tussen uw on-premises omgeving en Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Hoe los ik foutcode 450 4.4.318?

- Kijk welke scenario op u van toepassing is en breng de benodigde wijzigingen aan.

- Als het probleem wordt veroorzaakt door netwerkproblemen tussen uw on-premises omgeving en Microsoft 365, neemt u contact op met uw netwerkteam om dit probleem op te lossen.

- Neem contact op met uw partner om dit probleem op te lossen als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudservice provider).

## <a name="error-code-450-47320-certificate-validation-failed"></a>Foutcode: certificaatvalidatie 450 4.7.320 is mislukt

Dit betekent meestal dat Microsoft 365 een fout heeft ontdekt bij het valideren van het certificaat van de doel-e-mailserver. In de foutdetails wordt de fout uitgelegd. Bijvoorbeeld:

- Certificaat verlopen

- Certificaatonderwerp komt niet overeen

- Certificaat is niet langer geldig

### <a name="how-do-i-fix-error-code-450-47320"></a>Hoe los ik foutcode 450 4.7.320?

- Los het certificaat of de instellingen op de connector op, zodat berichten in de wachtrij in Microsoft 365 kunnen worden geleverd.

- Neem contact op met uw partner om dit probleem op te lossen als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudservice provider).

## <a name="other-error-codes"></a>Andere foutcodes

Microsoft 365 biedt problemen met het bezorgen van berichten aan uw on-premises e-mailserver of partner. Gebruik de **doelserver** gegevens in de fout om het probleem in uw omgeving te bekijken, of wijzig de connector als er een configuratiefout is opgetreden.

Neem contact op met uw partner om dit probleem op te lossen als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudservice provider).
