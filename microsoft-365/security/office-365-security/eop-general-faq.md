---
title: Algemene veelgestelde vragen over EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Hier vindt u antwoorden op de meest voorkomende algemene vragen over de e-mailfilterservice van Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0a5712d2bfb110c3292dee06b456161599d40b1
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165485"
---
# <a name="eop-general-faq"></a>Algemene veelgestelde vragen over EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige versie van Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)

Hier beantwoorden we de meest voorkomende algemene vragen over de EOP-filterservice (Exchange Online Protection) die in de cloud wordt gehost. Voor aanvullende veelgestelde vragen (veelgestelde vragen) gaat u naar de volgende koppelingen:

- [Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Veelgestelde vragen over gedelegeerd beheer](delegated-administration-faq.md)

- [Veelgestelde vragen over beveiliging tegen ongewenste e-mail](anti-spam-protection-faq.md)

- [Veelgestelde vragen over quarantaine](quarantine-faq.md)

- [Veelgestelde vragen over beveiliging tegen malware](anti-malware-protection-faq-eop.md)

- [Veelgestelde vragen over bericht traceren](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Wat is EOP?

EOP is een cloud-gehoste e-mailfilterservice die klanten beschermt tegen spam en malware en om aangepaste beleidsregels te implementeren. EOP is opgenomen in elk Microsoft 365-abonnement dat Exchange Online-postvakken bevat. EOP is ook beschikbaar als zelfstandige aanbieding ter bescherming van on-premises e-mailomgevingen.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Hoe meld ik me aan voor een proefversie van EOP of hoe koop ik EOP?

Meld u aan voor een proefversie van EOP of koop EOP via het web op de startpagina van [Exchange Online Protection.](https://products.office.com/exchange/exchange-email-security-spam-protection) Houd er rekening mee dat de functionaliteit voor een proefabonnement hetzelfde is als voor een betaald abonnement, maar ook de extra functies bevat die worden geleverd bij [het Exchange Enterprise CAL met Services-abonnement.](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview)

## <a name="how-is-eop-priced"></a>Hoe is EOP duur?

EOP wordt in licentie gegeven door de gebruiker. Zie de startpagina van Exchange Online Protection voor de [meest recente prijsinformatie.](https://products.office.com/exchange/exchange-email-security-spam-protection)

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Hoe lang duurt het om EOP in productie te nemen?

Wanneer u de MX-record wijzigt volgens de stappen in De [EOP-service](set-up-your-eop-service.md)instellen, en uw e-mail doorstroomt via EOP, wordt het filteren onmiddellijk gestart. Het kan 24-48 uur duren voordat de MX-record is doorgegeven via DNS. U kunt uw beveiligingsinstellingen op elk moment tijdens dit proces aanpassen.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>Moet ik alle functies van Microsoft 365 gebruiken om EOP te gebruiken? Wat als ik alleen EOP-beveiliging wil en dat is alles?

U kunt EOP gebruiken om uw on-premises postvakken te beveiligen zonder dat u andere functies van Microsoft 365 gebruikt. Dit wordt een zelfstandig abonnement genoemd. Een lijst met EOP-functies vindt u in de beschrijving van [de Exchange Online Protection-service.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Waarom heb ik een Microsoft 365-tenant nodig wanneer ik me aanmeldt voor e-mailfiltering via EOP?

Microsoft 365 is de naam die wordt gegeven aan een verzameling producten en services die mogelijk worden gebruikt via een Microsoft 365-tenant. De Microsoft 365-tenant is het beginpunt waar u licenties voor e-mailfiltering kunt toevoegen.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>Heeft EOP een communicatieportal waar ik meer kan weten over bekende problemen en verwachte oplossingen? Hoe zit het met nieuwe functies?

Het Microsoft 365-beheercentrum zal een deel van deze informatie bevatten. Als een gebeurtenis op serviceniveau uw gevolgen heeft, ziet u een communicatiewaarschuwing (meestal vergezeld van een belpictogram) nadat u zich hebt aanmeldt bij het Microsoft 365-beheercentrum. We raden u aan alle betreffende items te lezen en te handelen.

Met betrekking tot nieuwe EOP-functies, is de roadmap voor [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) voor Bedrijven een goede bron voor informatie over komende nieuwe functies. We plaatsen ook blogartikelen over nieuwe functies op de [website Microsoft 365 Blogs.](https://www.microsoft.com/microsoft-365/blog/)

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Werkt de service met oudere Exchange-versies (zoals Exchange Server 2010) en niet-Exchange-omgevingen?

Ja, de service is server-agnostic en kan worden gebruikt met elke SMTP-agent voor e-mailoverdracht.

## <a name="what-size-organization-can-use-the-service"></a>Hoe groot kan de organisatie de service gebruiken?

Elke grootte. Het EOP-netwerk heeft voldoende capaciteit om uw groei mogelijk te maken, ongeacht hoe snel uw organisatie groeit.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Welke machtigingen heb ik nodig om EOP in te stellen?

Als u EOP wilt configureren, moet u een globale beheerder zijn of een beheerder van een Exchange-bedrijf (de rollengroep Organisatiebeheer).

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Hoe weet ik of mijn gegevens en persoonlijke gegevens veilig zijn?

Ga naar het [Office 365](https://www.microsoft.com/trust-center)Vertrouwenscentrum voor meer informatie over de stappen die we hebben ondernomen om de veiligheid van uw gegevens en persoonlijke gegevens te waarborgen, inclusief informatie over serviceovereenkomsten (SLA's).

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Zijn er bepaalde limieten waar ik rekening mee moet houden, zoals de limieten voor de berichtgrootte?

Ja. Zie Exchange Online Protection-limieten voor meer informatie over [limieten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)in EOP.

## <a name="does-eop-support-powershell"></a>Ondersteunt EOP PowerShell?

Ja, de volledige EOP-functionaliteit is beschikbaar via PowerShell: Exchange Online PowerShell voor organisaties met Exchange Online-postvakken; zelfstandige EOP PowerShell voor zelfstandige EOP-organisaties. Zie Exchange [Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) en [Exchange Online Protection PowerShell voor meer informatie.](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)
