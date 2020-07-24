---
title: Inzicht in uw rekening of factuur
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Meer informatie over het lezen en begrijpen van uw factuur of factuur voor Zakelijke Microsoft-producten.
keywords: factureringsrekeningen, organisatiegegevens, facturen
ms.openlocfilehash: f0575683cdcaf0ac76de80c93e0d7573e8c63bae
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391516"
---
# <a name="understand-your-bill-or-invoice"></a>Inzicht in uw rekening of factuur

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

De factuur bevat een overzicht van uw kosten en betalingsinstructies. U [uw online factuur bekijken](#view-your-online-invoice) in het Microsoft 365-beheercentrum. U het ook downloaden in de Portable Document Format (.pdf) om te verzenden via e-mail.

Zie Uw [factuur of factuur voor Microsoft 365 voor bedrijven begrijpen](understand-your-invoice2.md)als u alleen een Microsoft 365-abonnement hebt.

## <a name="understand-the-invoice-header"></a>De factuurkop begrijpen

De bovenkant van de eerste pagina identificeert wie verantwoordelijk is voor betaling, waar de factuur naartoe wordt verzonden en een overzicht van de kosten.

| Termijn | Beschrijving |
| --- | --- |
| Verkocht aan |De factureringsrekening die de naam en het adres van de rechtspersoon identificeert die verantwoordelijk is voor de betaling. Deze informatie kan worden beheerd op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Factureringsaccounts,</a> waar u de accountovereenkomst vinden en rollen en machtigingen beheren. |
| Wetsvoorstel aan |Hiermee wordt aangegeven wie de factuur ontvangt. Deze informatie kan worden beheerd op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Factureringsprofielen.</a> Het factuurprofiel wordt ook weergegeven op de online factuurpagina, in het gedeelte **Factuuroverzicht.** Zie [Factureringsprofielen](manage-billing-profiles.md)beheren voor meer informatie over factureringsprofielen en hoe u deze gebruiken om flexibelere factureringsopties voor uw organisatie te maken. |
| Factureringsprofiel |De naam van het factureringsprofiel dat wordt gebruikt om factuureigenschappen te definiëren, zoals **Factuur-** **naar-, PO-nummer**en betalingsvoorwaarden. Deze informatie kan worden beheerd op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Factureringsprofielen.</a> Zie [Factureringsprofielen](manage-billing-profiles.md)beheren voor meer informatie over factureringsprofielen en hoe u deze gebruiken om flexibelere factureringsopties voor uw organisatie te maken. |
| Factuurnummer |Een uniek, door Microsoft gegenereerd factuurnummer dat wordt gebruikt voor trackingdoeleinden. |
| Factuurdatum |Datum waarop de factuur wordt gegenereerd, meestal vijf tot twaalf dagen na het einde van de factureringscyclus. U uw factuurdatum controleren op de pagina met de details van het factureringsprofiel. Kosten die plaatsvinden tussen het einde van de factureringsperiode en de factuurdatum worden opgenomen in de factuur voor de volgende maand, omdat ze zich in de volgende factureringsperiode bevinden. De begin- en einddatums van de factureringsperiode voor elke factuur worden vermeld in de factuur-PDF boven **factureringsoverzicht**.|
| Betalingsvoorwaarden |Hoe u betaalt voor uw Microsoft-factuur. *Netto 30 dagen* betekent dat u binnen 30 dagen na de factuurdatum de instructies op uw factuur opvolgt. |

## <a name="understand-the-billing-summary"></a>Het factureringsoverzicht begrijpen

De **factureringsoverzicht** toont de samenvatting van de kosten sinds de vorige factureringsperiode, eventuele credits die zijn toegepast, belasting en het totale verschuldigde bedrag.

| Termijn | Beschrijving |
| --- | --- |
| Kosten|Totaal aantal gekochte producten voor deze factureringsperiode en de bijbehorende kosten en belastingen. Aankopen worden samengevoegd om een beknopt overzicht van uw factuur te geven. |
| Tegoeden |Credits die je hebt ontvangen van retourzendingen |
| Azure-credits toegepast |Uw Azure-tegoedpunten die automatisch worden toegepast op Azure, brengen elke factureringsperiode kosten in rekening. Als u geen Azure-credits hebt, is dit veld verborgen. Zie Microsoft Customer Agreement [Azure-tegoed bijhouden](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance)voor meer informatie over Azure-credits. |
| Subtotaal |Het verschuldigde bedrag vóór belastingen |
| Belasting |Het type en het bedrag van de belasting die u betaalt, afhankelijk van het land van uw factureringsprofiel. Als u geen belasting hoeft te betalen, wordt er geen belasting op uw factuur weergegeven. |

### <a name="understand-your-charges"></a>Begrijp uw kosten

De kostenpagina's tonen de kosten uitgesplitst naar product. Voor Azure-klanten kunnen de kosten worden georganiseerd op factuursectie. Zie [Factuursecties](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections) in [Aan de slag met uw Factureringsaccount voor Microsoft-klantenovereenkomst](https://docs.microsoft.com/azure/billing/billing-mca-overview)voor meer informatie over de manier waarop factuursecties worden gebruikt met Azure-producten. Binnen elke productorder worden de kosten uitgesplitst naar servicefamilie.

| Termijn |Beschrijving |
| --- | --- |
| Eenheidsprijs | De effectieve eenheidsprijs van de service (in prijsvaluta) die wordt gebruikt om de kosten te berekenen. Deze prijs is uniek voor een product, servicefamilie, meter en aanbieding. |
| Veld | Hoeveelheid die tijdens de factureringsperiode is gekocht of verbruikt |
| Kosten/credits | Nettobedrag van de kosten na de toepassing van credits/terugbetalingen |
| Azure-tegoed | Het bedrag azure-tegoeden dat wordt toegepast op de kosten/credits |
| Belastingtarief | Belastingtarief, afhankelijk van het land |
| Belastingbedrag | Bedrag van de belasting toegepast op de aankoop op basis van belastingtarief |
| Totaal | Het totale bedrag dat verschuldigd is voor de aankoop |

Details van regelitems variëren afhankelijk van het type product waarvoor u kosten in rekening wordt gebracht. Voor Azure-producten wordt bijvoorbeeld het aantal toegepaste Azure-tegoeden weergegeven. Producten op basis van zitplaatsen tonen een eenheidsprijs en hoeveelheid. De factuurgegevens tonen de gekochte producten, korting of credits die zijn toegepast, belastingtarief en bedrag en de artikeltotalen van de regel.

> Totaal = Kosten - Azure-tegoed + belasting

Het totale bedrag dat voor elke servicefamilie verschuldigd is, wordt berekend door Azure-tegoeden af te trekken van credits/kosten en belasting toe te voegen:

> Totaal = Kosten/credits - Azure-tegoed + belasting

Zie Uw factuur voor de [overeenkomst met Microsoft-klantovereenkomst controleren](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill)als er Azure-kosten op uw factuur staan waarop u meer informatie wilt.

## <a name="understand-the-last-invoice-page"></a>De laatste factuurpagina begrijpen

### <a name="payment-instructions"></a>Betalingsinstructies

Onderaan de factuur staan instructies voor het betalen van uw factuur. U betalen via de telefoon, check, of online.

### <a name="publisher-information"></a>Uitgeversgegevens

Als u services van derden in uw factuur hebt staan, worden de naam en het adres van elke uitgever onder aan uw factuur vermeld.

## <a name="view-your-online-invoice"></a>Uw online factuur bekijken

Facturen zijn online beschikbaar. Een link naar uw online factuur is beschikbaar via uw PDF-factuur en via een e-mailmelding. De online factuur is uitbreidbaar, zodat u de kosten op uw factuur bekijken en meer details voor elk artikel bekijken. De online factuur bevat:

- **Prijsdetails** &mdash; Aanvullende informatie, waaronder details over kortingen en productprijzen.

- **Online betalen** &mdash; U ervoor kiezen om online een betaling te doen via de factuur.

- **Azure-kostenbeheer** &mdash; Voor Azure-klanten bevatten online facturen een koppeling naar Azure-kostenbeheer.

### <a name="to-view-your-online-invoice"></a>Uw online factuur bekijken

1. Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturen en betalingen</a>.

2. Als u de .pdf-versie van uw factuur wilt downloaden, kiest u **Factuur PDF downloaden** in de rij voor de factuur die u wilt zien.

3. Als u uw online factuur wilt bekijken, kiest u een factuur uit de lijst. U de .pdf ook downloaden van de pagina met factuurgegevens.

## <a name="invoice-faq"></a>Veelgestelde vragen over factuur

### <a name="when-is-my-invoice-available"></a>Wanneer is mijn factuur beschikbaar?

Sommige facturen worden gegenereerd binnen 24 uur na de aankoop. Andere facturen worden gegenereerd aan het einde van de factureringsperiode en bevatten alle artikelen uit die periode.

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>Hoe betaal ik het verschuldigde bedrag op mijn factuur?

Betalingsinstructies zijn afhankelijk van uw betalingsmethode en worden onder aan de factuur-PDF weergegeven. Als uw betalingsmethode een creditcard is, wordt deze automatisch in rekening gebracht binnen 10 dagen na de factuurdatum. Als uw betalingsmethode is door middel van controle of overschrijving, zie de informatie onder **Betalingsinstructies** in de PDF.

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>Wat is het verschil tussen 'Verkocht aan' en 'Factuur naar' adressen?

- **Verkocht aan:** De rechtspersoon die verantwoordelijk is voor de betaling en op de factuur is geïdentificeerd. Het hier opgegeven adres wordt gebruikt om uw belastingtarief te bepalen, tenzij u ervoor kiest om een alternatief verzendadres op te geven tijdens uw aankoop. Zie [Belastinginformatie](tax-information.md)voor meer informatie.
- **Factuur aan:** Het adres waar de fysieke factuur wordt verzonden, indien van toepassing. Er kunnen meerdere **bill to-adressen** per rechtspersoon zijn, maar slechts één **factuur om** per factureringsprofiel aan te pakken.

### <a name="what-are-billed-amount-and-amount-due"></a>Wat zijn 'Gefactureerd bedrag' en 'Verschuldigd bedrag?'

- **Gefactureerd bedrag:** Het totale bedrag voor de aankoop die u hebt gedaan.
- **Verschuldigd bedrag:** Het resterende saldo voor wat je verschuldigd bent.

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>Wat is het verschil tussen ''Serviceperiode' en 'Factureringsperiode?'

- **Serviceperiode:** De periode waarin u in rekening wordt gebracht om de service te gebruiken.
- **Factureringsperiode:** De periode sinds de laatste factuurdatum.

### <a name="how-do-i-view-and-print-my-bill"></a>Hoe kan ik mijn factuur weergeven en afdrukken?

1. Selecteer **Billing**op de pagina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Factureringsfacturen & een</a> factuurdatumbereik.
2. Als u een PDF-kopie van de factuur wilt afdrukken of opslaan, selecteert u **Factuur PDF downloaden**en vervolgens de PDF afdrukken.

[Zie Uw factuur of factuur weergeven](view-your-bill-or-invoice.md)voor meer informatie.

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>Waarom zie ik Azure-vooruitbetaling niet als betalingsmethode?

Azure-vooruitbetaling is alleen beschikbaar als betalingsmethode voor in aanmerking komende Azure-producten en -services.

## <a name="need-help-contact-support"></a>Hulp nodig? Neem contact op met ondersteuning.

Als u vragen hebt of hulp nodig hebt bij uw Azure-credits, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">maakt u een ondersteuningsverzoek met Azure-ondersteuning.</a>

Als u vragen hebt of hulp nodig hebt met uw factuur in het Microsoft 365-beheercentrum, neemt [u contact op met ondersteuning voor zakelijke producten.](../../admin/contact-support-for-business-products.md)