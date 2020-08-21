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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
ms.custom:
- seo-marvel-apr2020
description: Hier vindt u antwoorden op de meest voorkomende algemene vragen over de in de Cloud gehoste e-mail filterservice van Exchange Online Protection (EOP).
ms.openlocfilehash: 42162ea841f876fc5e958d67fab61dbe4bffe9de
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827759"
---
# <a name="eop-general-faq"></a>Algemene veelgestelde vragen over EOP

Hier beantwoorden we de meest voorkomende algemene vragen over Exchange Online Protection (EOP) in de Cloud gehoste e-mail filterservice. Ga naar de volgende koppelingen voor meer informatie over veelgestelde vragen over veelgestelde vragen:

- [Veelgestelde vragen over in een wachtrij geplaatste, uitgestelde en niet-bezorgde berichten in EOP](eop-queued-deferred-and-bounced-messages-faq.md)

- [Veelgestelde vragen over gedelegeerd beheer](delegated-administration-faq.md)

- [Veelgestelde vragen over beveiliging tegen ongewenste e-mail](anti-spam-protection-faq.md)

- [Veelgestelde vragen over quarantaine](quarantine-faq.md)

- [Veelgestelde vragen over beveiliging tegen malware](anti-malware-protection-faq-eop.md)

- [Veelgestelde vragen over bericht tracering](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq)

## <a name="what-is-eop"></a>Wat is EOP?

EOP is een door de Cloud gehoste e-mail filterservice die is ontwikkeld om klanten te beschermen tegen spam en malware, en om aangepaste beleidsregels te implementeren. EOP is opgenomen in een Microsoft 365-abonnement dat postvakken van Exchange Online bevat. EOP is ook beschikbaar als zelfstandige aanbieding om on-premises e-mail omgevingen te helpen beschermen.

## <a name="how-do-i-sign-up-for-an-eop-trial-or-purchase-eop"></a>Hoe meld ik me aan bij een EOP-proefversie of schaft u EOP?

Registreer u voor een EOP-proefversie of Koop EOP via het web op de [Startpagina van Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection). Houd er rekening mee dat de functionaliteit van een proefabonnement hetzelfde is als voor een betaald abonnement, maar ook de extra functies van het [Exchange Enterprise](https://products.office.com/exchange/microsoft-exchange-server-licensing-licensing-overview) -licentie schema met Services.

## <a name="how-is-eop-priced"></a>Hoe is EOP geprijsd?

De gebruiker heeft een licentie voor EOP. Zie de [Startpagina van Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection)voor de nieuwste prijsinformatie.

## <a name="how-long-does-it-take-to-put-eop-into-production"></a>Hoe lang duurt het om EOP in te stellen in de productie?

Als u uw MX-record wijzigt, wordt de stappen die worden beschreven in [uw EOP-service](set-up-your-eop-service.md)en uw e-mail stromen via EOP, onmiddellijk gestart. De MX-record kan lang duren, wat 24-48 uur duurt om via DNS door te geven. U kunt op elk gewenst moment uw beveiligingsinstellingen afstemmen tijdens dit proces.

## <a name="do-i-have-to-use-all-features-of-microsoft-365-to-use-eop-what-if-i-just-want-eop-protection-and-thats-all"></a>Moet ik alle functies van Microsoft 365 gebruiken om EOP te gebruiken? Wat moet ik doen als ik alleen EOP bescherming wil en dat allemaal?

U kunt EOP gebruiken om uw on-premises postvakken te beschermen zonder andere functies van Microsoft 365 te gebruiken. Dit wordt een standalone-abonnement genoemd. U vindt een lijst met EOP-functies in de [Beschrijving van de Exchange Online Protection-Service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="why-do-i-need-a-microsoft-365-tenant-when-signing-up-for-email-filtering-through-eop"></a>Waarom heb ik een Microsoft 365-Tenant nodig bij het aanmelden voor e-mail filtering via EOP?

Microsoft 365 is de naam die is toegewezen aan een verzameling producten en services die toegankelijk zijn via een Microsoft 365-Tenant. Denk na over de Microsoft 365-Tenant als uitgangspunt waarop u licenties voor e-mail filtering kunt toevoegen.

## <a name="does-eop-have-a-communication-portal-where-i-can-find-out-about-known-issues-and-expected-resolutions-what-about-new-features"></a>Heeft EOP een communicatie portal waar ik informatie kan vinden over bekende problemen en verwachte oplossingen? Hoe zit het met de nieuwe functies?

Het Microsoft 365-Beheercentrum heeft een deel van deze gegevens. Als u op een service niveau van invloed bent, ziet u een communicatie waarschuwing (meestal met een klokpictogram) nadat u zich hebt aangemeld bij het Microsoft 365-Beheercentrum. We raden u aan alle items die u nodig hebt, te lezen en te ondernemen.

Met betrekking tot de nieuwe EOP-functies is [Microsoft 365 for Business routekaart](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) een goede bron voor het vinden van informatie over aanstaande nieuwe functies. We posten ook blog artikelen over nieuwe functies op de website van [Microsoft 365 blogs](https://www.microsoft.com/microsoft-365/blog/) .

## <a name="does-the-service-work-with-legacy-exchange-versions-such-as-exchange-server-2010-and-non-exchange-environments"></a>Werkt de service met oudere Exchange-versies (zoals Exchange Server 2010) en niet-Exchange-omgevingen?

Ja, de service is server agnostic en kan worden gebruikt met een overdrachts agent voor SMTP-berichten.

## <a name="what-size-organization-can-use-the-service"></a>Welke grootte organisatie kan de service gebruiken?

Elke grootte. Het EOP-netwerk heeft voldoende capaciteit voor uw groei, ongeacht hoe snel uw organisatie groeit.

## <a name="what-permissions-do-i-need-to-set-up-eop"></a>Welke machtigingen heb ik nodig om EOP in te stellen?

Om EOP te configureren, moet u een globale beheerder of een beheerder van Exchange-bedrijf (de rollen groep Organisatiebeheer) zijn.

## <a name="how-do-i-know-my-data-and-private-information-are-safe"></a>Hoe weet ik of mijn gegevens en persoonlijke gegevens veilig zijn?

Ga naar het [Vertrouwenscentrum van Office 365](https://www.microsoft.com/trust-center)voor meer informatie over de stappen die we hebben ondernomen om de veiligheid van uw gegevens en persoonlijke gegevens, waaronder informatie over serviceniveau overeenkomsten (serviceniveau overeenkomsten), te zien.

## <a name="are-there-any-limits-i-should-be-aware-of-such-as-message-size-limitations"></a>Gelden er beperkingen, zoals beperkingen voor de berichtgrootte?

Ja. Zie [limieten voor Exchange Online-beveiliging](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)voor meer informatie over limieten in EOP.

## <a name="does-eop-support-powershell"></a>Ondersteunt EOP PowerShell?

U kunt de volledige functionaliteit van EOP beschikbaar stellen via PowerShell: Exchange Online PowerShell voor organisaties met postvakken van Exchange Online. Standalone EOP PowerShell voor zelfstandige EOP-organisaties. Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) en [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)voor meer informatie.
