---
title: Algemene veelgestelde vragen van EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
description: 'Hier beantwoorden we de meest voorkomende algemene vragen over de EOP-cloudfilterservice (Microsoft Exchange Online Protection) in de cloud. Ga voor aanvullende veelgestelde vragen (FAQ)-onderwerpen naar de volgende links:'
ms.openlocfilehash: 03fb070b2a40ad1e363138124eb0225e64fd5702
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42805283"
---
# <a name="eop-general-faq"></a>Algemene veelgestelde vragen van EOP

Hier beantwoorden we de meest voorkomende algemene vragen over de EOP-cloudfilterservice (Microsoft Exchange Online Protection) in de cloud. Ga voor aanvullende veelgestelde vragen (FAQ)-onderwerpen naar de volgende links:

- [Veelgestelde vragen over EOP in de wachtrij, uitgestelde en teruggestuurde berichten](eop-queued-deferred-and-bounced-messages-faq.md)

- [Veelgestelde vragen over gedelegeerd beheer](delegated-administration-faq.md)

- [Veelgestelde vragen over antispambescherming](anti-spam-protection-faq.md)

- [Lijsten met afzenders en geblokkeerde afzenders in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)

- [Veelgestelde vragen over quarantaine](quarantine-faq.md)

- [Veelgestelde vragen over anti-malwarebescherming](anti-malware-protection-faq-eop.md)

- [Veelgestelde vragen over berichttracering](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

**V. Wat is EOP?**

A. EOP is een door de cloud gehoste e-mailfilterservice die is gebouwd om klanten te beschermen tegen spam en malware en om aangepaste beleidsregels te implementeren.

**V. Hoe meld ik me aan voor een EOP-proefversie of koop ik EOP?**

A. Meld u aan voor een EOP-proefversie of koop EOP via het web op de startpagina van [Exchange Online Protection.](https://products.office.com/exchange/exchange-email-security-spam-protection) Houd er rekening mee dat de functionaliteit voor een proefabonnement hetzelfde is als voor een betaald abonnement, maar ook de extra functies bevat die zijn geleverd met het [Exchange Enterprise CAL met Services-abonnement.](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview)

**V. Hoe is EOP geprijsd?**

A. EOP heeft een licentie van gebruiker. Zie de startpagina van [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection)voor de laatste prijsinformatie.

**V. Hoe lang duurt het om EOP in productie te nemen?**

A. Wanneer u uw MX-record wijzigt, volgens de stappen die zijn beschreven in [Uw EOP-service instellen](set-up-your-eop-service.md)en uw e-mail via EOP stroomt, begint het filteren onmiddellijk. Het mx-record kan 24-48 uur duren om zich via DNS voort te planten. U uw beveiligingsinstellingen op elk gewenst moment tijdens dit proces afstemmen in het Exchange-beheercentrum (EAC).

**V. Moet ik alle functies van Microsoft Office 365 gebruiken om EOP te gebruiken? Wat als ik gewoon EOP bescherming wil en dat is alles?**

A. U EOP gebruiken om uw on-premises postvakken te beschermen zonder andere functies van Office 365 te gebruiken. Dit staat bekend als een zelfstandig abonnement. Een lijst met EOP-functies is te vinden in de beschrijving van de [Exchange Online Protection Service.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

**V. Waarom heb ik een Office 365-tenant nodig wanneer ik me aanmeldt voor e-mailfiltering via EOP?**

A. Office 365 is de naam die wordt gegeven aan een verzameling producten en services die toegankelijk zijn via een Office 365-tenant. Zie de Office 365-tenant als het startpunt waaraan u licenties toevoegen voor e-mailfiltering.

**V. Heeft EOP een communicatieportaal waar ik meer te weten kan komen over bekende problemen en verwachte oplossingen? Hoe zit het met nieuwe functies?**

A. Het Microsoft 365-beheercentrum zal een deel van deze informatie hebben. Als u wordt beïnvloed door een serviceniveaugebeurtenis, ziet u een communicatiewaarschuwing (meestal vergezeld van een belpictogram) nadat u zich hebt aanmeldde bij het Microsoft 365-beheercentrum. We raden u aan om items te lezen en waar nodig te reageren.

Wat nieuwe EOP-functies betreft, is de [roadmap Office 365 voor Bedrijven](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) een goede bron voor het vinden van informatie over aankomende nieuwe functies. We zullen ook het plaatsen van blog artikelen over nieuwe functies op de [Microsoft 365 Blogs](https://www.microsoft.com/microsoft-365/blog/) website.

**V. Werkt de service met verouderde Exchange-versies (zoals Exchange Server 2010) en niet-Exchange-omgevingen?**

A. Ja, de service is serveragnostisch en kan worden gebruikt met elke SMTP-e-mailtransferagent.

**V. Welke grootteorganisatie kan de service gebruiken?**

A. Elke maat. Het EOP-netwerk heeft voldoende capaciteit om uw groei op te vangen, hoe snel uw organisatie ook groeit.

**Welke machtigingen heb ik nodig om EOP in te stellen?**

Als u EOP wilt configureren, moet u een globale beheerder van Office 365 of een Exchange Company Administrator (de rolgroep Organisatiebeheer) zijn.

**V. Hoe weet ik dat mijn gegevens en privégegevens veilig zijn?**

A. Ga voor meer informatie over de stappen die we hebben genomen om de veiligheid van uw gegevens en privégegevens te garanderen, inclusief informatie over servicelevelovereenkomsten (SLA's), naar het [Office 365 Trust Center.](https://www.microsoft.com/trust-center)

**V. Zijn er limieten waarvan ik me bewust moet zijn, zoals beperkingen voor de grootte van berichten?**

A. Ja. Zie [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)voor meer informatie over limieten in EOP.

**V. Ondersteunt EOP PowerShell?**

A. Ja, volledige EOP-functionaliteit is beschikbaar via PowerShell. Zie [PowerShell voor onlinebescherming](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)van Exchange Online voor meer informatie.
