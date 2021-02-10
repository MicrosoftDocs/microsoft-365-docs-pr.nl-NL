---
title: Informatie over e-mailstroom
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
description: Beheerders kunnen meer informatie krijgen over de foutcodes die zijn gekoppeld aan berichtbezorging via connectors (ook wel bekend als mail flow intelligence).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 864b69bf650a4e460376ae988a9ce4abc4c61ad4
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167069"
---
# <a name="mail-flow-intelligence-in-eop"></a>E-mailstroomanalyse in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken gebruikt u meestal een connector om e-mailberichten vanuit EOP door te sturen naar uw on-premises e-mailomgeving. U kunt ook een connector gebruiken om berichten van Microsoft 365 door te sturen naar een partnerorganisatie. Als Microsoft 365 deze berichten niet via de connector kan bezorgen, worden deze in de wachtrij geplaatst in Microsoft 365. Microsoft 365 blijft de bezorging voor elk bericht 24 uur lang opnieuw proberen uit te proberen. Na 24 uur verloopt het bericht in de wachtrij en wordt het bericht geretourneerd aan de oorspronkelijke afzender in een rapport over niet-bezorging (ook wel een NDR- of niet-bezorgdbericht genoemd).

Microsoft 365 genereert een fout wanneer een bericht niet kan worden bezorgd via een connector. De meest voorkomende fouten en hun oplossingen worden in dit artikel beschreven. Wachtrij- en meldingsfouten voor niet-af te sluiten berichten die via connectors worden verzonden, worden ook wel informatie over _de e-mailstroom genoemd._

## <a name="error-code-450-44312-dns-query-failed"></a>Foutcode: 450 4.4.312 DNS-query is mislukt

Deze fout betekent meestal dat Microsoft 365 heeft geprobeerd verbinding te maken met de smart host die is opgegeven in de connector, maar dat de DNS-query om de IP-adressen van de smart host te vinden is mislukt. De mogelijke oorzaken voor deze fout zijn:

- Er is een probleem met de DNS-hostingservice van uw domein (de partij die de gezaghebbende naamservers voor uw domein onderhoudt).

- Uw domein is onlangs verlopen, dus de MX-record kan niet worden opgehaald.

- De MX-record van uw domein is onlangs gewijzigd en de DNS-servers hebben nog steeds DNS-gegevens in de cache opgeslagen voor uw domein.

### <a name="how-do-i-fix-error-code-450-44312"></a>Hoe kan ik foutcode 450 4.4.312 oplossen?

- Werk samen met uw DNS-hostingservice om het probleem met uw domein te identificeren en op te lossen.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), neem dan contact op met uw partner om het probleem op te lossen.

## <a name="error-code-450-44315-connection-timed-out"></a>Foutcode: 450 4.4.315 Time-out voor verbinding

Dit betekent meestal dat Microsoft 365 geen verbinding kan maken met de doel-e-mailserver. Aan de hand van de details van de fout wordt het probleem uitgelegd. Bijvoorbeeld:

- Uw on-premises e-mailserver is niet meer aanwezig.

- Er is een fout opgetreden in de smart host-instellingen van de connector, dus Microsoft 365 probeert verbinding te maken met het verkeerde IP-adres.

### <a name="how-do-i-fix-error-code-450-44315"></a>Hoe kan ik foutcode 450 4.4.315 oplossen?

- Zoek uit welk scenario op u van toepassing is en brengt de benodigde correcties aan. Als de e-mailstroom bijvoorbeeld goed werkt en u de instellingen van de connector niet hebt gewijzigd, moet u de on-premises e-mailomgeving controleren om te zien of de server niet is ingesteld of dat er wijzigingen zijn aangebracht in uw netwerkinfrastructuur (u hebt bijvoorbeeld internetproviders gewijzigd, zodat u nu verschillende IP-adressen hebt).

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), neem dan contact op met uw partner om het probleem op te lossen.

## <a name="error-code-450-44316-connection-refused"></a>Foutcode: 450 4.4.316 Verbinding geweigerd

Deze fout betekent meestal dat er een verbindingsfout is opgetreden in Microsoft 365 toen werd geprobeerd verbinding te maken met de doel-e-mailserver. Een mogelijke oorzaak voor deze fout is dat uw firewall verbindingen vanaf IP-adressen van Microsoft 365 blokkeert. Of deze fout kan komen als u uw on-premises e-mailsysteem volledig hebt gemigreerd naar Microsoft 365 en de on-premises e-mailomgeving hebt afgesloten.

### <a name="how-do-i-fix-error-code-450-44316"></a>Hoe kan ik foutcode 450 4.4.316 oplossen?

- Als uw on-premises omgeving postvakken heeft, moet u uw firewallinstellingen wijzigen om verbindingen van IP-adressen van Microsoft 365 op TCP-poort 25 met uw on-premises e-mailservers toe te staan. Zie URL's en IP-adresbereiken voor Microsoft 365 voor een lijst met De IP-adressen [van Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)

- Als er geen berichten meer moeten worden bezorgd in uw on-premises omgeving, klikt u **in** de waarschuwing op Nu herstellen, zodat Microsoft 365 de berichten met ongeldige geadresseerden direct kan weigeren. Hierdoor wordt het risico verkleind dat het quotum van uw organisatie voor ongeldige geadresseerden wordt overschreden, wat gevolgen kan hebben voor de normale bezorging van berichten. U kunt ook de volgende instructies gebruiken om het probleem handmatig op te lossen:

  - Schakel in [het Exchange-beheercentrum (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center)de connector uit die e-mail van Microsoft 365 naar uw on-premises e-mailomgeving bezorgt of verwijder deze:

    1. Ga in het EAC naar **Connectors voor de e-mailstroom.** \> 

    2. Selecteer de connector met de **Van-waarde** Office  **365** en de waarde **Aan** van de e-mailserver van uw organisatie en ga op een van de volgende stappen te werk:

       - De verbindingslijn verwijderen door op het **pictogram Verwijderen** ![ te klikken](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Schakel de connector uit door op het **pictogram** Bewerken ![ te klikken en De connector in te ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **schakelen.**

  - Wijzig het geaccepteerde domein in Microsoft 365 dat is  gekoppeld aan uw on-premises e-mailomgeving van Interne door te sturen in **Gezaghebbend.** Zie Geaccepteerd domeinen beheren [in Exchange Online voor instructies.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)

  **Opmerking:** Het duurt meestal 30 minuten tot een uur voordat deze wijzigingen van kracht worden. Controleer na een uur of de fout niet meer wordt weergegeven.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Foutcode: 450 4.4.317 Kan geen verbinding maken met een externe server

Deze fout betekent meestal dat Microsoft 365 is verbonden met de doel-e-mailserver, maar dat de server direct heeft gereageerd of niet voldoet aan de verbindingsvereisten. Aan de hand van de details van de fout wordt het probleem uitgelegd. Bijvoorbeeld:

- De doel-e-mailserver heeft gereageerd met de fout 'Service niet beschikbaar', wat aangeeft dat de server de communicatie met Microsoft 365 niet kan onderhouden.

- De connector is geconfigureerd voor het vereisen van TLS, maar de doel-e-mailserver biedt geen ondersteuning voor TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Hoe kan ik foutcode 450 4.4.317 oplossen?

- Controleer de TLS-instellingen en -certificaten op uw on-premises e-mailservers en de TLS-instellingen op de connector.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Foutcode: 450 4.4.318 Connection was closedly

Deze fout betekent meestal dat Microsoft 365 problemen heeft met de communicatie met uw on-premises e-mailomgeving, zodat de verbinding is weggevallen. De mogelijke oorzaken voor deze fout zijn:

- De firewall gebruikt SMTP-pakkettestregels en die regels werken niet goed.

- Uw on-premises e-mailserver werkt niet goed (bijvoorbeeld service loopt vast, crasht of lage systeembronnen), waardoor de server een time-out veroorzaakt en de verbinding met Microsoft 365 wordt gesloten.

- Er zijn netwerkproblemen tussen uw on-premises omgeving en Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Hoe kan ik foutcode 450 4.4.318 oplossen?

- Zoek uit welk scenario op u van toepassing is en brengt de benodigde correcties aan.

- Als het probleem wordt veroorzaakt door netwerkproblemen tussen uw on-premises omgeving en Microsoft 365, neem dan contact op met uw netwerkteam om het probleem op te lossen.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Foutcode: 450 4.7.320 Certificaatvalidatie is mislukt

Deze fout betekent meestal dat er in Microsoft 365 een fout is opgetreden tijdens het valideren van het certificaat van de doel-e-mailserver. In de details van de fout wordt de fout uitgelegd. Bijvoorbeeld:

- Certificaat verlopen

- Certificaatonderwerpen komen niet overeen

- Certificaat is niet meer geldig

### <a name="how-do-i-fix-error-code-450-47320"></a>Hoe kan ik foutcode 450 4.7.320 oplossen?

- Herstel het certificaat of de instellingen van de connector zodat berichten in de wachtrij in Microsoft 365 kunnen worden bezorgd.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.

## <a name="other-error-codes"></a>Andere foutcodes

Microsoft 365 heeft problemen met het bezorgen van berichten op uw on-premises e-mailserver of e-mailserver van een partner. Gebruik de **gegevens van de** doelserver in de fout om het probleem in uw omgeving te onderzoeken of wijzig de connector als er een configuratiefout is.

Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.
