---
title: Algemene veelgestelde vragen over EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Krijg antwoorden op de meest voorkomende algemene vragen over de Cloud-hosted e-mailfilteringservice (Exchange Online Protection) in de cloud.
ms.openlocfilehash: 02aa7175e95cf706ed13268035953400af2485a7
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206660"
---
# <a name="eop-general-faq"></a>Algemene veelgestelde vragen over EOP

Hier beantwoorden we de meest voorkomende algemene vragen over Exchange Online Protection (EOP) cloud-hosted e-mail filtering service. Ga voor aanvullende veelgestelde vragen (FAQ)-onderwerpen naar de volgende links:

- [Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Veelgestelde vragen over gedelegeerd beheer](delegated-administration-faq.md)

- [Veelgestelde vragen over beveiliging tegen ongewenste e-mail](anti-spam-protection-faq.md)

- [Veelgestelde vragen over quarantaine](quarantine-faq.md)

- [Veelgestelde vragen over beveiliging tegen malware](anti-malware-protection-faq-eop.md)

- [Veelgestelde vragen over berichttracering](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Wat is EOP?

EOP is een cloudgehoste e-mailfilterservice die is gebouwd om klanten te beschermen tegen spam en malware en om aangepaste beleidsregels te implementeren. EOP is opgenomen in elk Microsoft 365-abonnement dat Exchange Online-postvakken bevat. EOP is ook beschikbaar als een zelfstandig aanbod om on-premises e-mailomgevingen te beschermen.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Hoe meld ik me aan voor een EOP-proefversie of aankoop van EOP?

Meld u aan voor een EOP-proefversie of koop EOP via het web op de [startpagina van Exchange Online Protection.](https://products.office.com/exchange/exchange-email-security-spam-protection) Houd er rekening mee dat de functionaliteit voor een proefaankoop hetzelfde is als voor een betaald abonnement, maar ook de extra functies bevat die zijn geleverd met het [Exchange Enterprise CAL-abonnement met Services.](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview)

## <a name="how-is-eop-priced"></a>Hoe wordt EOP geprijsd?

EOP heeft een licentie van de gebruiker. Zie de startpagina van [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection)voor de meest recente prijsinformatie.

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Hoe lang duurt het om EOP in productie te nemen?

Wanneer u uw MX-record wijzigt, begint het filteren onmiddellijk, volgens de stappen die zijn beschreven in [Het instellen van uw EOP-service](set-up-your-eop-service.md)en uw e-mail via EOP. Het kan 24-48 uur duren voordat de MX-record wordt gepropageerd via DNS. U uw beveiligingsinstellingen op elk gewenst moment tijdens dit proces verfijnen.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>Moet ik alle functies van Microsoft 365 gebruiken om EOP te gebruiken? Wat als ik gewoon EOP bescherming wil en dat is alles?

U EOP gebruiken om uw on-premises postvakken te beschermen zonder andere functies van Microsoft 365 te gebruiken. Dit staat bekend als een zelfstandig abonnement. Een lijst met EOP-functies is te vinden in de Beschrijving van de [Exchange Online Protection Service.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Waarom heb ik een Microsoft 365-tenant nodig wanneer ik me aanmeldt voor e-mailfiltering via EOP?

Microsoft 365 is de naam die wordt gegeven aan een verzameling producten en services die toegankelijk zijn via een Microsoft 365-tenant. Denk aan de Microsoft 365-tenant als het startpunt waaraan u licenties voor e-mailfiltering toevoegen.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>Heeft EOP een communicatieportal waar ik meer te weten kan komen over bekende problemen en verwachte oplossingen? Hoe zit het met nieuwe functies?

Het Microsoft 365-beheercentrum heeft een deel van deze informatie. Als u wordt beïnvloed door een gebeurtenis op serviceniveau, ziet u een communicatiewaarschuwing (meestal vergezeld van een belpictogram) nadat u zich hebt aanmelden bij het Microsoft 365-beheercentrum. We raden u aan alle artikelen te lezen en ernaar te handelen.

Met betrekking tot nieuwe EOP-functies, de [Microsoft 365 voor bedrijven roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) is een goede bron voor het vinden van informatie over aankomende nieuwe functies. We zullen ook het plaatsen van blog artikelen over nieuwe functies op de [Microsoft 365 Blogs](https://www.microsoft.com/microsoft-365/blog/) website.

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Werkt de service met verouderde Exchange-versies (zoals Exchange Server 2010) en niet-Exchange-omgevingen?

Ja, de service is serveragnostisch en kan worden gebruikt met elke SMTP-e-mailoverdrachtagent.

## <a name="what-size-organization-can-use-the-service"></a>Welke grootte organisatie kan gebruik maken van de dienst?

Elke grootte. Het EOP-netwerk heeft voldoende capaciteit om uw groei aan te kunnen, hoe snel uw organisatie ook groeit.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Welke machtigingen heb ik nodig om EOP in te stellen?

Als u EOP wilt configureren, moet u een globale beheerder of een Exchange Company Administrator (de rolgroep Organisatiebeheer) zijn.

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Hoe weet ik of mijn gegevens en privégegevens veilig zijn?

Ga naar het [Office 365 Trust Center](https://www.microsoft.com/trust-center)voor meer informatie over de stappen die we hebben genomen om de veiligheid van uw gegevens en privégegevens te garanderen, inclusief informatie over SLA's (Service Level Agreements).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Zijn er limieten waar ik op moet letten, zoals beperkingen voor de grootte van berichten?

Ja. Zie [Exchange Online Protection Limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)voor meer informatie over limieten in EOP.

## <a name="does-eop-support-powershell"></a>Ondersteunt EOP PowerShell?

Ja, de volledige EOP-functionaliteit is beschikbaar via PowerShell: Exchange Online PowerShell voor organisaties met Exchange Online-postvakken; standalone EOP PowerShell voor standalone EOP-organisaties. Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell) en [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)voor meer informatie.
