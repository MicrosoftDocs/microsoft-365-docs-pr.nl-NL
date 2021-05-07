---
title: Berichtversleuteling
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het verzenden en ontvangen van versleutelde e-mailberichten tussen personen binnen en buiten uw organisatie.
ms.openlocfilehash: 504fa9918636cd596cde0d242083ccb7b9817e69
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162167"
---
# <a name="message-encryption"></a>Berichtversleuteling

Personen gebruiken vaak e-mail om gevoelige informatie uit te wisselen, zoals financiële gegevens, juridische contracten, vertrouwelijke productgegevens, verkooprapporten en projecties, gezondheidsgegevens van patiënten of klant- en werknemersgegevens. Als gevolg hiervan kunnen postvakken opslagplaatsen worden voor grote hoeveelheden mogelijk gevoelige informatie en kan het lekken van informatie een ernstige bedreiging voor uw organisatie worden.

Met Office 365-berichtversleuteling kan uw organisatie versleutelde e-mailberichten verzenden en ontvangen tussen personen binnen en buiten uw organisatie. Office 365-berichtversleuteling werkt met Outlook.com, Yahoo!, Gmail en andere e-mailservices. Versleuteling van e-mailberichten helpt ervoor te zorgen dat alleen beoogde geadresseerden berichtinhoud kunnen bekijken.

## <a name="how-office-365-message-encryption-works"></a>Hoe Office 365-berichtversleuteling werkt

De rest van dit artikel is van toepassing op de nieuwe OME-mogelijkheden.

Office 365-berichtversleuteling is een onlineservice die is gebaseerd op Microsoft Azure Rights Management (Azure RMS) die deel uitmaakt van Azure Information Protection. Deze service bevat versleutelings-, identiteits- en autorisatiebeleid om uw e-mail te beveiligen. U kunt berichten versleutelen met behulp van sjablonen voor rechtenbeheer, [de](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)optie Niet doorsturen en de optie [alleen-versleutelen.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

Gebruikers kunnen vervolgens e-mailberichten en verschillende bijlagen versleutelen met behulp van deze opties. Zie 'Bestandstypen die worden gedekt door IRM-beleid wanneer ze zijn gekoppeld aan berichten' in Inleiding tot IRM voor e-mailberichten voor een volledige lijst met [ondersteunde bijlagetypen.](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)

Als beheerder kunt u ook regels voor e-mailstroom definiëren om deze beveiliging toe te passen. U kunt bijvoorbeeld een regel maken die de versleuteling vereist van alle berichten die zijn geadresseerd aan een specifieke geadresseerde of die specifieke woorden in de onderwerpregel bevatten, en ook opgeven dat geadresseerden de inhoud van het bericht niet kunnen kopiëren of afdrukken.

In tegenstelling tot de vorige versie van OME bieden de nieuwe mogelijkheden een geïntegreerde afzenderervaring, ongeacht of u e-mail binnen uw organisatie verstuurt of naar geadresseerden buiten Microsoft 365. Bovendien hoeven geadresseerden die een beveiligd e-mailbericht ontvangen dat is verzonden naar een Microsoft 365-account in Outlook 2016 of Outlook op internet, geen andere actie te ondernemen om het bericht te bekijken. Het werkt naadloos. Ontvangers die andere e-mail clients en e-mailserviceproviders gebruiken, hebben ook een verbeterde ervaring. Zie Meer informatie over [beveiligde berichten in](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) Office 365 en Hoe open ik een beveiligd [bericht.](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)

Zie Versies van OME vergelijken voor een gedetailleerde lijst met de verschillen tussen de vorige versie van OME en de nieuwe [OME-mogelijkheden.](ome-version-comparison.md)

Wanneer iemand een e-mailbericht verzendt dat overeenkomt met een versleutelingsregel voor e-mailstroom, wordt het bericht versleuteld voordat het wordt verzonden. Alle Microsoft 365 eindgebruikers die Outlook-clients gebruiken om e-mail te lezen ontvangen native, eersteklas leeservaringen voor versleutelde en met rechten beveiligde e-mail, zelfs als ze zich niet in dezelfde organisatie als de afzender hebben. Ondersteunde Outlook-clients zijn Outlook bureaublad, Outlook Mac, Outlook mobiel op iOS en Android en Outlook op het web (voorheen bekend als Outlook Web App).

Ontvangers van versleutelde berichten die versleutelde of met rechten beveiligde e-mail ontvangen die naar hun Outlook.com-, Gmail- en Yahoo-accounts wordt verzonden, ontvangen een ingepakte e-mail die hen naar de OME Portal stuurt, waar ze zich eenvoudig kunnen verifiëren met een Microsoft-account, Gmail- of Yahoo-referenties.

Eindgebruikers die versleutelde of met rechten beveiligde e-mail lezen op andere clients dan Outlook gebruiken ook de OME-portal om versleutelde en met rechten beveiligde berichten weer te geven die ze ontvangen.

Als de afzender van de beveiligde e-mail zich in GCC Hoog en de ontvanger buiten GCC High, inclusief commerciële gebruikers, Outlook.com-gebruikers en gebruikers van andere e-mailproviders, zoals Gmail, heeft geplaatst, ontvangt de geadresseerde een ingepakte e-mail. De inwikkelmail leidt de geadresseerde naar de OME Portal waar de geadresseerde het bericht kan lezen en beantwoorden. Als de afzender en geadresseerde zich niet in de omgeving GCC High hebben, zelfs als ze zich niet in dezelfde organisatie hebben, dan ontvangen geadresseerden die Outlook-clients gebruiken voor het lezen van native, eersteklas leeservaringen voor versleutelde en met rechten beveiligde e-mail. Zie Versies van [OME](ome-version-comparison.md)vergelijken voor meer informatie over de verschillende GCC high.

Zie voor meer informatie over groottelimieten voor berichten en bijlagen die u kunt versleutelen met OME [Exchange Online Limieten.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Hoe Office 365 Advanced Message Encryption werkt boven op OME

Office 365 Advanced Message Encryption kunt u meerdere huisstijlsjablonen maken, zodat u de controle over geadresseerde-e-mail kunt aanpassen en aangepaste huisstijlervaringen kunt maken ter ondersteuning van een diverse organisatiestructuur.

Geavanceerde berichtversleuteling in Microsoft 365 helpt u te voldoen aan nalevingsverplichtingen die flexibelere controle vereisen over de toegang van externe geadresseerden tot versleutelde e-mailberichten. Met Geavanceerde berichtversleuteling in Office 365, als beheerder, kunt u gevoelige e-mailberichten die buiten de organisatie worden gedeeld, beheren met automatisch beleid dat gevoelige informatietypen (bijvoorbeeld PII-, financiële- of gezondheids-ID's) detecteert, of trefwoorden om de beveiliging te verbeteren door de toegang via een beveiligde webportal tot versleutelde e-mailberichten te verbeteren. Als beheerder kunt u versleutelde e-mailberichten die worden geopend via een Microsoft 365 webportal verder beheren door op elk gewenst moment de toegang tot een e-mail in te vragen.

Het intrekken en verlopen van berichten werkt alleen voor e-mailberichten die uw gebruikers verzenden naar geadresseerden buiten uw organisatie. Bovendien moeten de geadresseerden toegang hebben tot de e-mail via de webportal. Als u ervoor wilt zorgen dat de geadresseerde de portal gebruikt om e-mail te ontvangen, stelt u een aangepaste huisstijlsjabloon in waarin de wrapper wordt toegepast. Vervolgens kunt u de huisstijlsjabloon toepassen op een regel voor e-mailstroom. Zie voor meer informatie over geavanceerde berichtversleuteling [Office 365 Advanced Message Encryption.](ome-advanced-message-encryption.md)

## <a name="defining-rules-for-office-365-message-encryption"></a>Regels definiëren voor Office 365-berichtversleuteling

Een manier om de nieuwe mogelijkheden voor Office 365-berichtversleuteling in te Exchange Online en Exchange Online Protection beheerders om regels voor e-mailstroom te definiëren. Deze regels bepalen onder welke voorwaarden e-mailberichten moeten worden versleuteld. Wanneer een versleutelingsactie is ingesteld voor een regel, worden alle berichten die voldoen aan de regelvoorwaarden, versleuteld voordat ze worden verzonden.

E-mailstroomregels zijn flexibel, zodat u voorwaarden kunt combineren, zodat u in één regel aan specifieke beveiligingsvereisten kunt voldoen. U kunt bijvoorbeeld een regel maken om alle berichten te versleutelen die opgegeven trefwoorden bevatten en die zijn geadresseerd aan externe geadresseerden. De nieuwe mogelijkheden voor Office 365-berichtversleuteling versleutelen ook antwoorden van geadresseerden van versleutelde e-mail.

Zie Regels definiëren voor Office 365-berichtversleuteling voor meer informatie over het maken van regels voor e-mailstroom om te profiteren van de nieuwe [OME-mogelijkheden.](define-mail-flow-rules-to-encrypt-email.md)

## <a name="get-started-with-the-new-ome-capabilities"></a>Aan de slag met de nieuwe OME-mogelijkheden

Als u klaar bent om aan de slag te gaan met de nieuwe [OME-mogelijkheden](set-up-new-message-encryption-capabilities.md)binnen uw organisatie, zie Nieuwe functies Office 365-berichtversleuteling instellen.

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Versleutelde e-mailberichten verzenden, weergeven en beantwoorden

Met Office 365-berichtversleuteling kunnen gebruikers versleutelde e-mail verzenden vanaf Outlook en Outlook op internet. Daarnaast kunnen beheerders regels voor e-mailstroom instellen in Microsoft 365 om e-mailberichten automatisch te versleutelen op basis van trefwoordmatching of andere voorwaarden.

Ontvangers van versleutelde berichten in organisaties kunnen deze berichten naadloos lezen in elke versie van Outlook, waaronder Outlook voor pc, Outlook voor Mac, Outlook op het web, Outlook voor iOS en Outlook voor Android. Gebruikers die versleutelde berichten ontvangen op andere e-mail clients, kunnen de berichten bekijken in de OME-portal.

Bekijk deze artikelen voor gedetailleerde informatie over het verzenden en weergeven van versleutelde berichten.

|Lees dit artikel...|Als u...|
|:-----|:-----|
|[Meer informatie over beveiligde berichten in Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|Een eindgebruiker die meer wil weten over hoe versleutelde berichten werken en welke opties voor u beschikbaar zijn.|
|[Hoe open ik een beveiligd bericht?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|Een eindgebruiker die een beveiligd bericht wil lezen dat naar u is verzonden. Dit artikel bevat informatie over het lezen van berichten in verschillende versies van Outlook en uit verschillende e-mailaccounts, waaronder die accounts buiten Microsoft 365 zoals Gmail en Yahoo! accounts.|
|[Versleutelde berichten verzenden, weergeven en beantwoorden in Outlook](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|Een eindgebruiker die een versleuteld bericht wil verzenden, weergeven of beantwoorden vanuit Outlook. Zelfs als u geen lid bent van een organisatie, ontvangt u nog steeds een melding van versleutelde berichten die naar u zijn verzonden in Outlook. Gebruik dit artikel voor instructies over het weergeven en beantwoorden van versleutelde berichten die zijn verzonden vanaf Office 365.|
|[Een digitaal ondertekend of versleuteld bericht verzenden](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Een eindgebruiker die versleutelde berichten wil verzenden, weergeven of beantwoorden met Outlook voor Mac. In dit artikel wordt ook beschreven hoe u andere versleutelingsmethoden gebruikt dan OME, zoals S/MIME.|
|[Versleutelde berichten weergeven op uw Android-apparaat](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Een eindgebruiker die een bericht heeft ontvangen dat is versleuteld met Office 365-berichtversleuteling op uw Android-apparaat, kunt u de gratis APP OME Viewer gebruiken om het bericht te bekijken en een versleuteld antwoord te verzenden. In dit artikel wordt uitgelegd hoe u dit kunt doen.|
|[Versleutelde berichten weergeven op uw iPhone of iPad](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|Een eindgebruiker die een bericht heeft ontvangen dat is versleuteld met Office 365-berichtversleuteling op uw iPhone of iPad, kunt u de gratis APP OME Viewer gebruiken om het bericht te bekijken en een versleuteld antwoord te verzenden. In dit artikel wordt uitgelegd hoe u dit kunt doen.|
||