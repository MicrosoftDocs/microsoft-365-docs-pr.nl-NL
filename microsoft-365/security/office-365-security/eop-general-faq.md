---
title: Algemene veelgestelde vragen over EOP
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
ms.custom:
- seo-marvel-apr2020
description: In dit onderwerp vindt u de meest voorkomende algemene vragen over de Microsoft Exchange Online Protection (EOP) cloud-gehoste e-mailfilterservice.
ms.openlocfilehash: 48841e5e68dd560329eadc0a654e6d8fe1b2d09e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036558"
---
# <a name="eop-general-faq"></a>Algemene veelgestelde vragen over EOP

Hier beantwoorden we de meest voorkomende algemene vragen over de Microsoft Exchange Online Protection (EOP) cloud-hosted e-mailfilteringservice. Ga voor aanvullende veelgestelde vragen (FAQ)-onderwerpen naar de volgende links:

- [Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Veelgestelde vragen over gedelegeerd beheer](delegated-administration-faq.md)

- [Veelgestelde vragen over beveiliging tegen ongewenste e-mail](anti-spam-protection-faq.md)

- [Veelgestelde vragen over quarantaine](quarantine-faq.md)

- [Veelgestelde vragen over beveiliging tegen malware](anti-malware-protection-faq-eop.md)

- [Veelgestelde vragen over berichttracering](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

**V. Wat is EOP?**

A. EOP is een cloudgehoste e-mailfilterservice die is gebouwd om klanten te beschermen tegen spam en malware en om aangepaste beleidsregels te implementeren.

**V. Hoe meld ik me aan voor een EOP-proefversie of aankoop van EOP?**

A. Meld u aan voor een EOP-proefversie of koop EOP via het web op de [startpagina van Exchange Online Protection.](https://products.office.com/exchange/exchange-email-security-spam-protection) Houd er rekening mee dat de functionaliteit voor een proefaankoop hetzelfde is als voor een betaald abonnement, maar ook de extra functies bevat die zijn geleverd met het [Exchange Enterprise CAL-abonnement met Services.](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview)

**V. Hoe wordt EOP geprijsd?**

A. EOP heeft een licentie van de gebruiker. Zie de startpagina van [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection)voor de meest recente prijsinformatie.

**V. Hoe lang duurt het om EOP in productie te nemen?**

A. Wanneer u uw MX-record wijzigt, begint het filteren onmiddellijk, volgens de stappen die zijn beschreven in [Het instellen van uw EOP-service](set-up-your-eop-service.md)en uw e-mail via EOP. Het kan 24-48 uur duren voordat de MX-record wordt gepropageerd via DNS. U uw beveiligingsinstellingen tijdens dit proces op elk gewenst moment in het Exchange-beheercentrum (EAC) verfijnen.

**V. Moet ik alle functies van Microsoft 365 gebruiken om EOP te gebruiken? Wat als ik gewoon EOP bescherming wil en dat is alles?**

A. U EOP gebruiken om uw on-premises postvakken te beschermen zonder andere functies van Microsoft 365 te gebruiken. Dit staat bekend als een zelfstandig abonnement. Een lijst met EOP-functies is te vinden in de Beschrijving van de [Exchange Online Protection Service.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

**V. Waarom heb ik een Microsoft 365-tenant nodig wanneer ik me aanmeldt voor e-mailfiltering via EOP?**

A. Microsoft 365 is de naam die wordt gegeven aan een verzameling producten en services die toegankelijk zijn via een Microsoft 365-tenant. Denk aan de Microsoft 365-tenant als het startpunt waaraan u licenties voor e-mailfiltering toevoegen.

**V. Heeft EOP een communicatieportal waar ik meer te weten kan komen over bekende problemen en verwachte oplossingen? Hoe zit het met nieuwe functies?**

A. Het Microsoft 365-beheercentrum heeft een deel van deze informatie. Als u wordt beïnvloed door een gebeurtenis op serviceniveau, ziet u een communicatiewaarschuwing (meestal vergezeld van een belpictogram) nadat u zich hebt aanmelden bij het Microsoft 365-beheercentrum. We raden u aan alle artikelen te lezen en ernaar te handelen.

Met betrekking tot nieuwe EOP-functies, de [Microsoft 365 voor bedrijven roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) is een goede bron voor het vinden van informatie over aankomende nieuwe functies. We zullen ook het plaatsen van blog artikelen over nieuwe functies op de [Microsoft 365 Blogs](https://www.microsoft.com/microsoft-365/blog/) website.

**V. Werkt de service met verouderde Exchange-versies (zoals Exchange Server 2010) en niet-Exchange-omgevingen?**

A. Ja, de service is serveragnostisch en kan worden gebruikt met elke SMTP-e-mailoverdrachtagent.

**V. Welke grootte organisatie kan de service gebruiken?**

A. Elke grootte. Het EOP-netwerk heeft voldoende capaciteit om uw groei aan te kunnen, hoe snel uw organisatie ook groeit.

**Welke machtigingen heb ik nodig om EOP in te stellen?**

Als u EOP wilt configureren, moet u een globale beheerder of een Exchange Company Administrator (de rolgroep Organisatiebeheer) zijn.

**V. Hoe weet ik of mijn gegevens en privégegevens veilig zijn?**

A. Ga naar het [Office 365 Trust Center](https://www.microsoft.com/trust-center)voor meer informatie over de stappen die we hebben genomen om de veiligheid van uw gegevens en privégegevens te garanderen, inclusief informatie over SLA's (Service Level Agreements).

**V. Zijn er limieten waar ik rekening mee moet houden, zoals beperkingen voor de grootte van berichten?**

A. Ja. Zie [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)voor meer informatie over limieten in EOP.

**V. Ondersteunt EOP PowerShell?**

A. Ja, volledige EOP-functionaliteit is beschikbaar via PowerShell. Zie [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)voor meer informatie.
