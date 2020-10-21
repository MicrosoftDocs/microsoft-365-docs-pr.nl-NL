---
title: Inzicht in uw rekening of factuur
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
description: Lees hoe u uw factuur of factuur voor Microsoft Business Products kunt lezen en begrijpen.
keywords: facturerings accounts, organisatiegegevens, facturen
ms.openlocfilehash: 80b7e4f14390e2f695dc753358f9e5bebe055bd0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638409"
---
# <a name="understand-your-bill-or-invoice"></a>Inzicht in uw rekening of factuur

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

De factuur bevat een overzicht van uw kosten en instructies voor de betaling. U kunt [uw online factuur weergeven](#view-your-online-invoice) in het microsoft 365-Beheercentrum. U kunt de app ook downloaden in de PDF-indeling (Portable Document Format) om per e-mail te verzenden.

Zie [informatie over uw rekening of factuur voor Microsoft 365 voor bedrijven](understand-your-invoice2.md)als u slechts een abonnement op microsoft 365 hebt.

## <a name="understand-the-invoice-header"></a>Meer informatie over de factuurkop

Boven aan de eerste pagina wordt aangegeven wie er kan worden betaald, waarbij de factuur wordt verzonden en een kostenoverzicht.

| Term | Beschrijving |
| --- | --- |
| Verkocht aan |De factureringsrekening die de naam en het adres identificeert van de rechtspersoon die verantwoordelijk is voor de betaling. U kunt deze informatie beheren op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">facturerings accounts</a> , waarop u de overeenkomst met de account kunt vinden en rollen en machtigingen kunt beheren. |
| Factureren aan |Identificeert wie de factuur ontvangt. U kunt deze informatie beheren op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">facturerings profielen</a> . Het facturerings profiel wordt ook op de pagina online factuur weergegeven in de sectie **Factuuroverzicht** . Zie [facturerings profielen beheren](manage-billing-profiles.md)voor meer informatie over facturerings profielen en de manier waarop u deze kunt gebruiken voor het maken van flexibele factureringsopties voor uw organisatie. |
| Facturerings profiel |De naam van het facturerings profiel dat wordt gebruikt voor het definiëren van factuur eigenschappen, zoals **Facturering naar**, **PO-nummer**en betalingsvoorwaarden. U kunt deze informatie beheren op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">facturerings profielen</a> . Zie [facturerings profielen beheren](manage-billing-profiles.md)voor meer informatie over facturerings profielen en hoe u deze kunt gebruiken voor het maken van flexibele factureringsopties voor uw organisatie. |
| Factuurnummer |Een uniek, door Microsoft aangemaakt factuurnummer voor tracking doeleinden. |
| Factuurdatum |Datum waarop de factuur is gegenereerd, meestal vijf tot 12 dagen na het einde van de factureringscyclus. U kunt de factuurdatum controleren op de pagina Details van factuur profiel. Kosten tussen het einde van de factuurperiode en de factuurdatum worden opgenomen in de factuur voor de volgende maand, aangezien deze zich in de volgende factuurperiode bevinden. De begin-en einddatum van de factureringsperiode voor elke factuur worden weergegeven in het PDF-factuur boven de **facturerings samenvatting**.|
| Betalingsvoorwaarden |Hoe u betaalt voor uw Microsoft-factuur. *Netto 30 dagen* houdt in dat u binnen 30 dagen na de factuurdatum betaalt met de volgende instructies op uw factuur. |

## <a name="understand-the-billing-summary"></a>Inzicht in de facturerings samenvatting

Het **Overzicht facturering** toont het kostenoverzicht van de kosten sinds de vorige factureringsperiode, alle kredieten die zijn toegepast, belastingen en het totale verschuldigde bedrag.

| Term | Beschrijving |
| --- | --- |
| Kosten|Het totaal aantal gekochte producten voor deze factuurperiode en de gerelateerde kosten en belastingen. Aankopen worden geaggregeerd om een beknopt overzicht van uw factuur te geven. |
| Tegoeden |Tegoed dat u hebt ontvangen van retour resultaten |
| Azure-tegoeden toegepast |Uw Azure-tegoeden worden automatisch toegepast op Azure kost elke factureringsperiode. Als u geen Azure-tegoed hebt, is dit veld verborgen. Zie [Microsoft Customer Agreement Azure tegoed saldo bijhouden](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance)voor meer informatie over Azure-tegoeden. |
| Subtotaal |Het voorbelastingen verschuldigd bedrag |
| Belasting |Het type en het BTW-tarief dat u betaalt, afhankelijk van het land van uw facturerings profiel. Als u geen BTW hoeft te betalen, wordt er geen BTW weergegeven op uw factuur. |

### <a name="understand-your-charges"></a>Meer informatie over uw kosten

Op de pagina kosten worden de kosten per product weergegeven. Voor Azure-klanten kunnen de kosten sectie per factuur worden ingedeeld. Zie [factuur secties](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections) in [aan de slag met uw Microsoft-factureringsaccount](https://docs.microsoft.com/azure/billing/billing-mca-overview)voor meer informatie over de manier waarop factuur secties worden gebruikt met Azure-producten. In elke productorder worden de kosten per servicepakket uitgesplitst.

| Term |Beschrijving |
| --- | --- |
| Prijs per stuk | De effectieve prijs per eenheid van de service (in de valuta prijs) die wordt gebruikt voor het berekenen van de kosten. Deze prijs is uniek voor een product, service familie, meter en aanbieding. |
| Verbruik | Aangeschafte hoeveelheid of verbruikt tijdens de factureringsperiode |
| Kosten/tegoeden | De hoeveelheid kosten na betaling van de tegoed |
| Azure-tegoed | De hoeveelheid Azure tegoeden die zijn toegepast op de kosten/kredieten |
| BTW-tarief | BTW-tarief, afhankelijk van het land |
| BTW-bedrag | BTW-tarief dat op het aankoopbedrag is toegepast op basis van een BTW-tarief |
| Totaal | Het totale verschuldigde bedrag voor de aankoop |

Details regelitems zijn afhankelijk van het type product waarvoor u de kosten in rekening brengt. Voor Azure-producten wordt bijvoorbeeld het bedrag van de toegepaste Azure-tegoeden weergegeven. Producten op basis van de stoel tonen een prijs per eenheid en een hoeveelheid. De details van de factuur bevatten de producten die zijn gekocht, korting of kredieten, en de totalen van de regelitems.

> Totaal = kosten-Azure tegoed + BTW

Het totale verschuldigde bedrag voor elk servicepakket wordt berekend door Azure-tegoed af te trekken van tegoeden/kosten en het toevoegen van belastingen:

> Totaal = kosten/tegoeden-Azure tegoed + BTW

Zie [uw factuur voor Microsoft Customer Agreement controleren](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill)als er Azure kosten op uw factuur waarover u meer wilt weten.

## <a name="understand-the-last-invoice-page"></a>Meer informatie over de laatste factuur pagina

### <a name="payment-instructions"></a>Betalingsinstructies

Onder aan de factuur vindt u instructies voor het betalen van uw factuur. U kunt betalen via een kabel, cheque of online.

### <a name="publisher-information"></a>Info over Uitgever

Als uw factuur van derden gebruikmaakt, wordt de naam en het adres van elke uitgever weergegeven onder aan de factuur.

## <a name="view-your-online-invoice"></a>Uw online factuur weergeven

Facturen zijn online beschikbaar. Een koppeling naar uw online factuur is beschikbaar in uw PDF-factuur en vanuit een e-mail melding. De online factuur is uitbreidbaar, zodat u de kosten op uw factuur kunt bekijken en meer Details voor elk item kunt zien. De online factuur omvat:

- **Prijsdetails** &mdash; Aanvullende informatie inclusief details over kortingen en productprijzen.

- **Online betaling** &mdash; U kunt ervoor kiezen een betaling online te doen op de factuur.

- Beheer van Azure **kosten** &mdash; Voor Azure-klanten bevat online facturen een koppeling naar Azure Cost Management.

### <a name="to-view-your-online-invoice"></a>Uw online factuur weergeven

1. Ga in het Beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturen en betalingen</a>.

2. Als u de PDF-versie van de factuur wilt downloaden, kiest u **invoice PDF downloaden** in de rij voor de factuur die u wilt weergeven.

3. Als u uw online factuur wilt bekijken, kiest u een factuur in de lijst. U kunt het PDF-bestand ook downloaden via de pagina Details van factuur.

## <a name="invoice-faq"></a>Veelgestelde vragen over facturen

### <a name="when-is-my-invoice-available"></a>Wanneer is mijn factuur beschikbaar?

Sommige facturen worden binnen 24 uur na de aankoop gegenereerd. Er worden andere facturen gegenereerd aan het einde van de factureringsperiode en alle items uit die periode worden opgenomen.

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>Hoe betaal ik het verschuldigde bedrag op mijn factuur?

Betalingsinstructies zijn afhankelijk van uw betalingsmethode en worden onder aan het PDF-bestand aan de factuur geboden. Als uw betalingsmethode een creditcard is, wordt deze automatisch in rekening gebracht binnen 10 dagen na de factuurdatum. Als uw betalingswijze via cheque of overschrijving is, raadpleegt u de informatie onder **betalingsinstructies** in het PDF-bestand.

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>Wat is het verschil tussen de adressen ' verkocht aan ' en ' factuur '?

- **Verkocht aan:** De rechtspersoon die verantwoordelijk is voor de betaling en die is geïdentificeerd op de factuur. Het door u opgegeven adres wordt gebruikt om uw BTW-tarief te bepalen, tenzij u tijdens uw aankoop een alternatief verzendadres moet opgeven. Zie [belastinginformatie](tax-information.md)voor meer informatie.
- **Factureren aan:** Het adres waar de fysieke factuur wordt verzonden, indien van toepassing. Er kunnen meerdere facturen per rechtspersoon worden **gefactureerd** , maar één factuur **voor** adres per facturerings profiel.

### <a name="what-are-billed-amount-and-amount-due"></a>Wat zijn de bedragen gefactureerd bedrag en het verschuldigde bedrag?

- **Gefactureerd bedrag:** Het totale bedrag voor de aankoop die u hebt gemaakt.
- **Verschuldigde bedrag:** Het resterende saldo van wat u hebt verschuldigd.

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>Wat is het verschil tussen "' service periode ' en ' factuurperiode? '.

- **Service periode:** De termijn waarbinnen u in rekening wordt gebracht voor het gebruik van de service.
- **Factureringsperiode:** De tijdsperiode sinds de laatste factuurdatum.

### <a name="how-do-i-view-and-print-my-bill"></a>Hoe kan ik mijn factuur weergeven en afdrukken?

1. Selecteer een factuurdatum bereik op de pagina **facturerings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">rekeningen & betalingen</a> .
2. Als u een PDF-versie van de factuur wilt afdrukken of opslaan, selecteert u **PDF-versie van factuur downloaden**en drukt u vervolgens op het PDF-bestand.

Zie [uw rekening of factuur weergeven](view-your-bill-or-invoice.md)voor meer informatie.

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>Waarom zie ik geen Azure-vooruitbetaling als betalingswijze?

Azure-vooruitbetaling is alleen beschikbaar als een betaalwijze voor de in aanmerking komende Azure-product en-services.

## <a name="need-help-contact-support"></a>Hulp nodig? Neem contact op met ondersteuning.

Als u vragen hebt of hulp nodig hebt bij uw Azure-tegoed, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">maakt u een ondersteuningsverzoek met Azure-ondersteuning</a>.

[Neem contact op met de ondersteuning voor zakelijke producten](../../admin/contact-support-for-business-products.md)als u vragen hebt of hulp nodig hebt bij uw factuur in microsoft 365-Beheercentrum.