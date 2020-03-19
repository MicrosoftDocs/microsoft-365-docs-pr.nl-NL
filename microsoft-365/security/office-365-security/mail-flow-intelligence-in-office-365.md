---
title: Informatie over e-mailstroom in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Beheerders kunnen meer te weten komen over de foutcodes die zijn gekoppeld aan het bezorgen van berichten met behulp van connectors in Office 365 (ook wel mailflow intelligence genoemd).
ms.openlocfilehash: 849493cefecb3344eaf7b6db73be3930138c236c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806298"
---
# <a name="mail-flow-intelligence-in-office-365"></a>Informatie over e-mailstroom in Office 365

Normaal gesproken gebruikt u een connector om e-mailberichten van uw Office 365-organisatie door te sturen naar uw on-premises e-mailomgeving. U ook een connector gebruiken om berichten van Office 365 naar een partnerorganisatie te routeren. Wanneer Office 365 deze berichten niet via de connector kan verzenden, staan ze in de wachtrij in Office 365. Office 365 blijft de bezorging voor elk bericht 24 uur opnieuw proberen. Na 24 uur verloopt het bericht in de wachtrij en wordt het bericht teruggestuurd naar de oorspronkelijke afzender in een rapport zonder levering (ook wel een NDR- of bouncebericht genoemd).

Office 365 genereert een fout wanneer een bericht niet kan worden geleverd met behulp van een connector. De meest voorkomende fouten en hun oplossingen worden beschreven in dit onderwerp. Gezamenlijk staan wachtrij- en meldingsfouten voor niet-leverbare berichten die via connectors worden verzonden, bekend als _mailflow intelligence._

## <a name="error-code-450-44312-dns-query-failed"></a>Foutcode: DNS-query 450 4.4.312 is mislukt

Deze fout betekent doorgaans dat Office 365 heeft geprobeerd verbinding te maken met de slimme host die is opgegeven in de connector, maar de DNS-query om de IP-adressen van de slimme host te vinden, is mislukt. De mogelijke oorzaken voor deze fout zijn:

- Er is een probleem met de DNS-hostingservice van uw domein (de partij die de gezaghebbende naamservers voor uw domein onderhoudt).

- Uw domein is onlangs verlopen, zodat de MX-record niet kan worden opgehaald.

- De MX-record van uw domein is onlangs gewijzigd en de DNS-servers van Office 365 hebben nog steeds eerder DNS-gegevens voor uw domein in de cache opgeslagen.

### <a name="how-do-i-fix-error-code-450-44312"></a>Hoe los ik foutcode 450 4.4.312 op?

- Werk samen met uw DNS-hostingservice om het probleem met uw domein te identificeren en op te lossen.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), neemt u contact op met uw partner om het probleem op te lossen.

## <a name="error-code-450-44315-connection-timed-out"></a>Foutcode: er is een time-out van de verbindingscode 450 4.4.315

Dit betekent doorgaans dat Office 365 geen verbinding kan maken met de e-mailserver van de bestemming. De foutdetails verklaren het probleem. Bijvoorbeeld:

- Uw on-premises e-mailserver is uitgeschakeld.

- Er is een fout in de slimme hostinstellingen van de connector, dus Office 365 probeert verbinding te maken met het verkeerde IP-adres.

### <a name="how-do-i-fix-error-code-450-44315"></a>Hoe los ik foutcode 450 4.4.315 op?

- Ontdek welk scenario op u van toepassing is en breng de nodige correcties aan. Als de e-mailstroom bijvoorbeeld correct heeft gewerkt en u de verbindingsinstellingen niet hebt gewijzigd, moet u uw on-premises e-mailomgeving controleren om te zien of de server is uitgeschakeld of als er wijzigingen zijn aangebracht in uw netwerkinfrastructuur (bijvoorbeeld u van internetprovider veranderd bent, dus u hebt nu verschillende IP-adressen).

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), neemt u contact op met uw partner om het probleem op te lossen.

## <a name="error-code-450-44316-connection-refused"></a>Foutcode: 450 4.4.316 Verbinding geweigerd

Deze fout betekent doorgaans dat Office 365 een verbindingsfout heeft ondervonden toen het verbinding probeerde te maken met de e-mailserver van de bestemming. Een waarschijnlijke oorzaak van deze fout is dat uw firewall verbindingen blokkeert van IP-adressen in Office 365. Deze fout kan ook worden gemaakt als u uw on-premises e-mailsysteem volledig hebt gemigreerd naar Office 365 en uw on-premises e-mailomgeving hebt afgesloten.

### <a name="how-do-i-fix-error-code-450-44316"></a>Hoe los ik foutcode 450 4.4.316 op?

- Als u postvakken in uw on-premises omgeving hebt, moet u uw firewall-instellingen wijzigen om verbindingen van Office 365 IP-adressen op TCP-poort 25 toe te staan met uw on-premises e-mailservers. Zie [URL's en IP-adresbereiken van Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)voor een lijst met de IP-adressen van Office 365.

- Als er geen berichten meer naar uw on-premises omgeving worden verzonden, klikt u nu in de waarschuwing op **Fix,** zodat Office 365 de berichten met ongeldige ontvangers onmiddellijk kan weigeren. Dit vermindert het risico van overschrijding van het quotum van uw organisatie voor ongeldige ontvangers, wat van invloed kan zijn op de normale berichtbezorging. U ook de volgende instructies gebruiken om het probleem handmatig op te lossen:

  - Schakel in het [Exchange-beheercentrum (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365 de connector uit die e-mail van Office 365 naar uw on-premises e-mailomgeving levert uit of verwijder deze:

    1. Ga in de EAC naar **Mail flow** \> **Connectors**.

    2. Selecteer de connector met **de** **Van-waarde Office 365** en **de** **e-mailserver** van uw organisatie en doe een van de volgende stappen:

       - De connector verwijderen door op pictogram **Verwijderen** ![te klikken](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Schakel de connector **Edit** ![uit door op](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) het pictogram Bewerken bewerken te klikken en schakel **het uitschakeling in .**

  - Wijzig het geaccepteerde domein in Office 365 dat is gekoppeld aan uw on-premises e-mailomgeving van **Intern relay** naar **gezaghebbend**. Zie [Geaccepteerde domeinen beheren in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)voor instructies .

  **Opmerking:** Deze wijzigingen duren doorgaans tussen de 30 minuten en een uur. Controleer na een uur of u de fout niet meer ontvangt.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Foutcode: 450 4.4.317 Kan geen verbinding maken met externe server

Deze fout betekent doorgaans dat Office 365 is verbonden met de e-mailserver van de bestemming, maar de server heeft onmiddellijk gereageerd op een fout of niet voldoet aan de verbindingsvereisten. De foutdetails verklaren het probleem. Bijvoorbeeld:

- De e-mailserver van de bestemming heeft gereageerd met een fout 'Service niet beschikbaar', wat aangeeft dat de server de communicatie met Office 365 niet kan onderhouden.

- De connector is geconfigureerd om TLS te vereisen, maar de e-mailserver van de bestemming ondersteunt TLS niet.

### <a name="how-do-i-fix-error-code-450-44317"></a>Hoe los ik foutcode 450 4.4.317 op?

- Controleer de TLS-instellingen en -certificaten op uw on-premises e-mailservers en de TLS-instellingen op de connector.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Foutcode: 450 4.4.318 Verbinding werd abrupt gesloten

Deze fout betekent doorgaans dat Office 365 moeite heeft met het communiceren met uw on-premises e-mailomgeving, zodat de verbinding is verbroken. De mogelijke oorzaken voor deze fout zijn:

- Uw firewall maakt gebruik van SMTP-regels voor pakketonderzoek en deze regels werken niet goed.

- Uw on-premises e-mailserver werkt niet correct (bijvoorbeeld serviceloopt, loopt vast of systeembronnen is laag), waardoor de server een time-out krijgt en de verbinding met Office 365 wordt gesloten.

- Er zijn netwerkproblemen tussen uw on-premises omgeving en Office 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Hoe los ik foutcode 450 4.4.318 op?

- Ontdek welk scenario op u van toepassing is en breng de nodige correcties aan.

- Als het probleem wordt veroorzaakt door netwerkproblemen tussen uw on-premises omgeving en Office 365, neemt u contact op met uw netwerkteam om het probleem op te lossen.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Foutcode: validatie 450 4.7.320 certificaat is mislukt

Deze fout betekent doorgaans dat er een fout is opgetreden in Office 365 tijdens het valideren van het certificaat van de e-mailserver van de bestemming. De foutdetails verklaren de fout. Bijvoorbeeld:

- Certificaat verlopen

- Mismatch certificaatonderwerp

- Certificaat is niet langer geldig

### <a name="how-do-i-fix-error-code-450-47320"></a>Hoe los ik foutcode 450 4.7.320 op?

- Bevestig het certificaat of de instellingen op de connector, zodat berichten in de wachtrij in Office 365 kunnen worden bezorgd.

- Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.

## <a name="other-error-codes"></a>Andere foutcodes

Office 365 heeft moeite met het bezorgen van berichten op uw on-premises of partnere-mailserver. Gebruik de **doelservergegevens** in de fout om het probleem in uw omgeving te onderzoeken of de connector te wijzigen als er een configuratiefout optreedt.

Als de fout afkomstig is van uw partnerorganisatie (bijvoorbeeld een externe cloudserviceprovider), moet u contact opnemen met uw partner om het probleem op te lossen.
