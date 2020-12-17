---
title: Inzicht in je rekening of factuur
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Ontdek hier hoe je je factuur of rekening voor zakelijke Microsoft-producten kunt lezen en begrijpen.
keywords: factureringsaccounts, organisatie info, facturen
ms.openlocfilehash: 80b7e4f14390e2f695dc753358f9e5bebe055bd0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638409"
---
# <a name="understand-your-bill-or-invoice"></a>Inzicht in je rekening of factuur

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat je gewend bent, raadpleeg je [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Op de factuur staan een kostenoverzicht en de betalingsinstructies vermeld. Je kunt [de online factuur bekijken](#view-your-online-invoice) in het Microsoft 365-beheercentrum. Je kunt de factuur ook in de Portable Document Format-indeling (.pdf) downloaden om deze per e-mail te verzenden.

Als je alleen een Microsoft 365-abonnement hebt, raadpleeg je [Inzicht in je rekening of factuur voor Microsoft 365 voor Bedrijven](understand-your-invoice2.md).

## <a name="understand-the-invoice-header"></a>Informatie over de koptekst van de factuur

De bovenkant van de eerste pagina geeft aan wie moet betalen, waar de factuur naartoe wordt verzonden en een kostenoverzicht.

| Term | Beschrijving |
| --- | --- |
| Verkocht aan |Het factureringsaccount met de naam en het adres van de rechtspersoon die voor de betaling verantwoordelijk is. Deze informatie kan worden beheerd op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Factureringsaccounts</a>, waar je de accountovereenkomst kunt vinden en rollen en machtigingen kunt beheren. |
| Factureren aan |Hiermee wordt aangegeven wie de factuur ontvangt. Deze informatie kan worden beheerd op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Factureringsprofielen</a>. Het Factureringsprofiel wordt ook weergegeven op de online factuurpagina in de sectie **Factuuroverzicht**. Voor meer informatie over factureringsprofielen en hoe je deze kunt gebruiken om flexibelere factureringsopties voor je organisatie te maken, raadpleeg je [Factureringsprofielen beheren](manage-billing-profiles.md). |
| Factureringsprofiel |De naam van het factureringsprofiel dat wordt gebruikt om de factuureigenschappen te definiëren, zoals **Factureren aan**, **Bestelnummer** en betalingsvoorwaarden. Deze informatie kan worden beheerd op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Factureringsprofielen</a>. Voor meer informatie over factureringsprofielen en hoe je deze kunt gebruiken om flexibelere factureringsopties voor je organisatie te maken, raadpleeg je [Factureringsprofielen beheren](manage-billing-profiles.md). |
| Factuurnummer |Een uniek, door Microsoft gegenereerd factuurnummer dat wordt gebruikt voor traceringsdoeleinden. |
| Factuurdatum |De datum waarop de factuur is gegenereerd, meestal 5 tot 12 dagen na het eind van de factureringscyclus. Je kunt de factuurdatum controleren op de detailpagina van factureringsprofiel. Kosten die tussen het einde van de factureringsperiode en de factuurdatum worden gemaakt, worden opgenomen in de factuur voor de volgende maand, omdat ze in de volgende factureringsperiode vallen. De begin- en einddatum van de factureringsperiode van elke factuur worden boven het **Factuuroverzicht** in de pdf-factuur weergegeven.|
| Betalingsvoorwaarden |De manier waarop je je Microsoft-factuur betaalt. *30 dagen netto* houdt in dat je binnen 30 dagen na de factuurdatum betaalt volgens de instructies op de factuur. |

## <a name="understand-the-billing-summary"></a>Inzicht in het factuuroverzicht

In het **Factuuroverzicht** wordt een kostenoverzicht sinds de vorige factureringsperiode weergegeven, alle eventueel toegepaste tegoeden, belasting en het totale verschuldigde bedrag.

| Term | Beschrijving |
| --- | --- |
| Kosten|Het totale aantal producten dat is gekocht tijdens deze factureringsperiode en de bijbehorende kosten en belastingen. Aankopen worden samengevoegd voor een beknopte weergave van de factuur. |
| Tegoeden |Tegoeden die je hebt ontvangen voor retouren |
| Toegepaste Azure-tegoeden |De Azure-tegoeden die elke factureringsperiode automatisch worden toegepast op de Azure-kosten. Als je geen Azure-tegoeden hebt, is dit veld verborgen. Raadpleeg voor meer informatie over Azure-tegoeden het artikel [Saldo van Azure-tegoed voor Microsoft-klantovereenkomst bijhouden](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance). |
| Subtotaal |Het verschuldigde bedrag vóór belastingen |
| Belasting |Het type en het bedrag aan belasting dat je betaalt, afhankelijk van het land van je factureringsprofiel. Als je geen belasting hoeft te betalen, wordt er geen belasting op de factuur weergegeven. |

### <a name="understand-your-charges"></a>Inzicht in je kosten

Op de kostenpagina worden de kosten per product weergegeven. Voor Azure-klanten zijn de kosten mogelijk gerangschikt op factuursectie. Voor meer informatie over de manier waarop factuursecties bij Azure-producten worden gebruikt, raadpleeg je [factuursecties](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections) in [Aan de slag met je factureringsaccount voor Microsoft-klantovereenkomst](https://docs.microsoft.com/azure/billing/billing-mca-overview). Binnen elke productorder worden kosten uitgesplitst per servicepakket.

| Term |Beschrijving |
| --- | --- |
| Prijs per eenheid | De daadwerkelijke prijs per eenheid van de service (in de prijsvaluta) die wordt gebruikt voor het berekenen van de kosten. Deze prijs is uniek voor een product, servicepakket, meter of aanbieding. |
| Aantal | Gekocht of verbruikt aantal tijdens de factureringsperiode |
| Kosten/tegoeden | Nettokostenbedrag na toegepaste tegoeden/restituties |
| Azure-tegoed | Het bedrag aan Azure-tegoed dat op de Kosten/tegoeden is toegepast |
| Belastingtarief | Belastingtarief, afhankelijk van het land |
| Belastingbedrag | Belastingbedrag dat op de aankoop is toegepast op basis van het belastingtarief |
| Totaal | Het totale verschuldigde bedrag voor de aankoop |

De gegevens van regelitems variëren afhankelijk van het type in rekening gebrachte product. Bij Azure-producten wordt bijvoorbeeld de bedrag aan toegepaste Azure-tegoeden weergegeven. Bij producten op basis van seats worden de prijs per eenheid en het aantal weergeven. De factuurgegevens bevatten de producten die zijn gekocht, de korting of de tegoedbedragen die zijn toegepast, het belastingtarief en -bedrag en de totalen per regelitem.

> Totaal = kosten - Azure-tegoed + belasting

Het totale verschuldigde bedrag voor elk servicepakket wordt berekend door Azure-tegoeden af te trekken van de kosten/tegoeden en door de belasting toe te voegen:

> Totaal = kosten/tegoeden - Azure-tegoed + belasting

Als er Azure-kosten op de factuur staan waarover je meer informatie wilt, raadpleeg je [Je factuur voor je Microsoft-klantovereenkomst controleren](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill).

## <a name="understand-the-last-invoice-page"></a>Inzicht in de laatste factuurpagina

### <a name="payment-instructions"></a>Betalingsinstructies

Onderaan de factuur staan instructies voor het betalen van de factuur. Je kunt betalen per bankoverschrijving, cheque of online.

### <a name="publisher-information"></a>Uitgeversinformatie

Als er services van derden op de factuur staan, worden de naam en het adres van elke uitgever onderaan de factuur weergegeven.

## <a name="view-your-online-invoice"></a>Je factuur online bekijken

Facturen zijn online beschikbaar. Er is een koppeling naar je online factuur beschikbaar in je pdf-factuur en vanuit een e-mailmelding. De online factuur kan worden uitgevouwen, zodat je de kosten op de factuur kunt bekijken en meer details voor elk item kunt lezen. De online factuur omvat:

- **Prijsinformatie**&mdash;Extra informatie, inclusief informatie over kortingen en productprijzen.

- **Online betaling**&mdash;Je kunt ervoor kiezen om vanuit de factuur online te betalen.

- **Azure Cost Management**&mdash;Bij Azure-klanten bevatten online facturen een koppeling naar Azure Cost Management.

### <a name="to-view-your-online-invoice"></a>Je factuur online bekijken

1. Ga in het Beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturen en betalingen</a>.

2. Als je de pdf-versie van de factuur wilt downloaden, kies je **Pdf-factuur downloaden** in de rij van de factuur die je wilt bekijken.

3. Als je de online factuur wilt bekijken, kies je een factuur in de lijst. Je kunt ook het pdf-bestand downloaden op de pagina Factuurgegevens.

## <a name="invoice-faq"></a>Veelgestelde vragen over facturen

### <a name="when-is-my-invoice-available"></a>Wanneer is mijn factuur beschikbaar?

Sommige facturen worden binnen 24 uur na de aankoop gegenereerd. Andere facturen worden aan het eind van de factureringsperiode gegenereerd en bevatten alle items uit die periode.

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>Hoe kan ik het verschuldigde bedrag op mijn factuur betalen?

De betalingsinstructies zijn afhankelijk van je betalingswijze en worden onderaan de pdf-factuur vermeld. Als je een creditcard als betalingswijze gebruikt, worden de kosten automatisch in rekening gebracht binnen 10 dagen na de factuurdatum. Als je een cheque of overschrijving als betalingswijze gebruikt, raadpleeg je de informatie onder **Betalingsinstructies** in het pdf-bestand.

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>Wat is het verschil tussen het 'verkocht aan'- en het 'factureren aan'-adres?

- **Verkocht aan:** De rechtspersoon die voor de betaling verantwoordelijk is en die op de factuur staat vermeld. Het hier opgegeven adres wordt gebruikt om het belastingtarief vast te stellen, tenzij je tijdens je aankoop een alternatief verzendadres opgeeft. Bekijk [Belastinginformatie](tax-information.md) voor meer informatie.
- **Factureren aan:** Het adres waar de fysieke factuur naartoe wordt verzonden, indien van toepassing. Er kunnen meerdere **Factureren aan**-adressen per rechtspersoon zijn, maar slechts één **Factureren aan** per factureringsprofiel.

### <a name="what-are-billed-amount-and-amount-due"></a>Wat is het 'gefactureerd bedrag' en het 'verschuldigd bedrag'?

- **Gefactureerd bedrag:** het totale bedrag voor de aankoop dat je hebt gedaan.
- **Verschuldigd bedrag:** het resterende saldo dat je verschuldigd bent.

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>Wat is het verschil tussen de 'serviceperiode' en de 'factureringsperiode'?

- **Serviceperiode:** De tijdsperiode waarvoor het gebruik van de service in rekening wordt gebracht.
- **Factureringsperiode:** De tijdsperiode sinds de laatste factuurdatum.

### <a name="how-do-i-view-and-print-my-bill"></a>Hoe kan ik mijn factuur weergeven en afdrukken?

1. Selecteer op de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturen en betalingen</a> een datumbereik voor de factuur.
2. Als je een pdf-versie van de factuur wilt afdrukken of opslaan, kies je **Pdf-factuur bekijken** en maak je vervolgens een afdruk van het pdf-bestand.

Zie [Je rekening of factuur bekijken](view-your-bill-or-invoice.md) voor meer informatie.

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>Waarom zie ik geen Azure-vooruitbetaling als betalingsmethode?

De Azure-vooruitbetaling is alleen als betaalmethode beschikbaar voor in aanmerking komende Azure-producten en -services.

## <a name="need-help-contact-support"></a>Hulp nodig? Neem contact op met ondersteuning.

Als je vragen hebt of hulp nodig hebt bij je Azure-tegoeden kun je <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">een ondersteuningsaanvraag maken bij ondersteuning voor Azure</a>.

Als je vragen hebt of hulp nodig hebt bij je factuur in het Microsoft 365-beheercentrum kun je [contact opnemen met ondersteuning voor zakelijke producten](../../admin/contact-support-for-business-products.md).