---
title: E-mailstroominformatie
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Beheerders kunnen meer informatie krijgen over de foutcodes die zijn gekoppeld aan berichtbezorging via verbindingslijnen (ook wel bekend als e-mailstroominformatie).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2cb52e5865415440b3b2924a3ebcc96a7f8e17e5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057925"
---
# <a name="mail-flow-intelligence-in-eop"></a>E-mailstroomanalyse in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken gebruikt u meestal een verbindingslijn om e-mailberichten van EOP naar uw on-premises e-mailomgeving te sturen. U kunt ook een verbindingslijn gebruiken om berichten van Microsoft 365 door te sturen naar een partnerorganisatie. Wanneer Microsoft 365 deze berichten niet kan bezorgen via de connector, worden ze in de wachtrij geplaatst in Microsoft 365. Microsoft 365 blijft de bezorging voor elk bericht 24 uur lang opnieuw proberen. Na 24 uur verloopt het bericht in de wachtrij en wordt het bericht geretourneerd naar de oorspronkelijke afzender in een rapport zonder bezorging (ook wel een NDR- of bouncebericht genoemd).

Microsoft 365 genereert een fout wanneer een bericht niet kan worden bezorgd via een verbindingslijn. De meest voorkomende fouten en hun oplossingen worden in dit artikel beschreven. In de rij- en meldingsfouten voor niet-besleedbare berichten die via verbindingslijnen worden verzonden, wordt _e-mailstroomintelligentie genoemd._

## <a name="error-code-450-44312-dns-query-failed"></a>Foutcode: DNS-query 450 4.4.312 is mislukt

Deze fout betekent meestal dat Microsoft 365 heeft geprobeerd verbinding te maken met de slimme host die is opgegeven in de connector, maar de DNS-query om de IP-adressen van de slimme host te zoeken is mislukt. De mogelijke oorzaken voor deze fout zijn:

- Er is een probleem met de DNS-hostingservice van uw domein (de partij die de gezaghebbende naamservers voor uw domein onderhoudt).

- Uw domein is onlangs verlopen, dus de MX-record kan niet worden opgehaald.

- De MX-record van uw domein is onlangs gewijzigd en de DNS-servers hebben nog steeds DNS-gegevens in de cache voor uw domein.

### <a name="how-do-i-fix-error-code-450-44312"></a>Hoe kan ik foutcode 450 4.4.312 oplossen?

- Werk samen met uw DNS-hostingservice om het probleem met uw domein te identificeren en op te lossen.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), neem dan contact op met uw partner om het probleem op te lossen.

## <a name="error-code-450-44315-connection-timed-out"></a>Foutcode: time-out van 450 4.4.315 Connection

Dit betekent meestal dat Microsoft 365 geen verbinding kan maken met de doel-e-mailserver. In de foutdetails wordt het probleem uitgelegd. Bijvoorbeeld:

- Uw on-premises e-mailserver is niet aanwezig.

- Er is een fout opgetreden in de instellingen voor slimme host van de connector, dus Microsoft 365 probeert verbinding te maken met het verkeerde IP-adres.

### <a name="how-do-i-fix-error-code-450-44315"></a>Hoe kan ik foutcode 450 4.4.315 oplossen?

- Zoek uit welk scenario op u van toepassing is en maak de benodigde correcties. Als de e-mailstroom bijvoorbeeld correct werkt en u de connectorinstellingen niet hebt gewijzigd, moet u uw on-premises e-mailomgeving controleren om te zien of de server niet actief is of als er wijzigingen zijn aangebracht in uw netwerkinfrastructuur (u hebt bijvoorbeeld internetproviders gewijzigd, zodat u nu verschillende IP-adressen hebt).

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), neem dan contact op met uw partner om het probleem op te lossen.

## <a name="error-code-450-44316-connection-refused"></a>Foutcode: 450 4.4.316 Verbinding geweigerd

Deze fout betekent meestal dat Microsoft 365 een verbindingsfout heeft ondervonden bij het maken van verbinding met de doel-e-mailserver. Een waarschijnlijke oorzaak voor deze fout is dat uw firewall verbindingen blokkeert via IP-adressen van Microsoft 365. Of deze fout kan zijn ontworpen als u uw on-premises e-mailsysteem volledig hebt gemigreerd naar Microsoft 365 en uw on-premises e-mailomgeving hebt afgesloten.

### <a name="how-do-i-fix-error-code-450-44316"></a>Hoe kan ik foutcode 450 4.4.316 oplossen?

- Als u postvakken in uw on-premises omgeving hebt, moet u de firewallinstellingen wijzigen om verbindingen van Microsoft 365 IP-adressen op TCP-poort 25 met uw on-premises e-mailservers toe te staan. Zie URL's en IP-adresbereiken van Microsoft 365 voor een lijst met de IP-adressen van [Microsoft 365.](../../enterprise/urls-and-ip-address-ranges.md)

- Als er geen berichten meer moeten worden bezorgd in uw on-premises omgeving, klikt u **op** Nu oplossen in de waarschuwing, zodat Microsoft 365 de berichten met ongeldige geadresseerden onmiddellijk kan weigeren. Hierdoor wordt het risico verkleind dat het quotum van uw organisatie voor ongeldige geadresseerden wordt overschreden, wat van invloed kan zijn op de normale berichtbezorging. U kunt ook de volgende instructies gebruiken om het probleem handmatig op te lossen:

  - Schakel in [het Exchange-beheercentrum (EAC)](/Exchange/exchange-admin-center)de connector uit of verwijder deze die e-mail van Microsoft 365 naar uw on-premises e-mailomgeving bezorgt:

    1. Ga in het EAC naar **E-mailstroomconnectoren.** \> 

    2. Selecteer de verbindingslijn **met de waarde Van** Office **365** en **de** e-mailserver van uw organisatie aan waarde en ga op een van de volgende stappen te werk: 

       - De verbindingslijn verwijderen door op **pictogram Verwijderen** ![ te klikken](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Schakel de verbindingslijn uit door op **pictogram Bewerken** ![ bewerken te klikken en Schakel Deze ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **in.**

  - Wijzig het geaccepteerde domein in Microsoft 365 dat is gekoppeld aan uw on-premises e-mailomgeving van **Interne** doorverteller in **Gezaghebbend.** Zie Geaccepteerde domeinen beheren in Exchange Online voor [instructies.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)

  **Opmerking:** Meestal duurt het 30 minuten tot een uur voordat deze wijzigingen van kracht worden. Controleer na één uur of u de fout niet meer ontvangt.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), moet u contact opnemen met uw partner om het probleem op te lossen.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Foutcode: 450 4.4.317 Kan geen verbinding maken met externe server

Deze fout betekent meestal dat Microsoft 365 is verbonden met de doel-e-mailserver, maar dat de server met een directe fout heeft gereageerd of niet voldoet aan de verbindingsvereisten. In de foutdetails wordt het probleem uitgelegd. Bijvoorbeeld:

- De doel-e-mailserver heeft gereageerd met een foutmelding 'Service niet beschikbaar', wat aangeeft dat de server de communicatie met Microsoft 365 niet kan onderhouden.

- De connector is geconfigureerd om TLS te vereisen, maar de doel-e-mailserver biedt geen ondersteuning voor TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Hoe kan ik foutcode 450 4.4.317 oplossen?

- Controleer de TLS-instellingen en -certificaten op uw on-premises e-mailservers en de TLS-instellingen op de connector.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), moet u contact opnemen met uw partner om het probleem op te lossen.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Foutcode: 450 4.4.318 Verbinding is plotseling gesloten

Deze fout betekent meestal dat Microsoft 365 problemen heeft met de communicatie met uw on-premises e-mailomgeving, zodat de verbinding is gestopt. De mogelijke oorzaken voor deze fout zijn:

- Uw firewall gebruikt SMTP-regels voor pakketonderzoek en deze regels werken niet correct.

- Uw on-premises e-mailserver werkt niet goed (bijvoorbeeld service loopt vast, loopt vast of er zijn systeembronnen laag), waardoor de server een time-out heeft en de verbinding met Microsoft 365 sluit.

- Er zijn netwerkproblemen tussen uw on-premises omgeving en Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Hoe kan ik foutcode 450 4.4.318 oplossen?

- Zoek uit welk scenario op u van toepassing is en maak de benodigde correcties.

- Als het probleem wordt veroorzaakt door netwerkproblemen tussen uw on-premises omgeving en Microsoft 365, neem dan contact op met uw netwerkteam om het probleem op te lossen.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), moet u contact opnemen met uw partner om het probleem op te lossen.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Foutcode: 450 4.7.320 Certificaatvalidatie is mislukt

Deze fout betekent meestal dat microsoft 365 een fout heeft ondervonden tijdens het valideren van het certificaat van de doel-e-mailserver. De foutdetails verklaren de fout. Bijvoorbeeld:

- Certificaat is verlopen

- Certificaatonderwerp komt niet overeen

- Certificaat is niet meer geldig

### <a name="how-do-i-fix-error-code-450-47320"></a>Hoe kan ik foutcode 450 4.7.320 oplossen?

- Herstel het certificaat of de instellingen op de connector, zodat berichten in de wachtrij in Microsoft 365 kunnen worden bezorgd.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), moet u contact opnemen met uw partner om het probleem op te lossen.

## <a name="other-error-codes"></a>Andere foutcodes

Microsoft 365 heeft problemen met het verzenden van berichten naar uw on-premises e-mailserver of partner-e-mailserver. Gebruik de **doelservergegevens** in de fout om het probleem in uw omgeving te onderzoeken of wijzig de verbindingslijn als er een configuratiefout is.

Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een cloudserviceprovider van derden), moet u contact opnemen met uw partner om het probleem op te lossen.