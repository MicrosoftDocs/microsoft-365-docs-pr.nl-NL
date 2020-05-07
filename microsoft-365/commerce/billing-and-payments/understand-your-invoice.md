---
title: Inzicht in uw factuur
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
ms.custom: ''
search.appverid:
- MET150
description: Meer informatie over het lezen en begrijpen van uw factuur voor Microsoft-bedrijfsproducten.
keywords: factureringsrekeningen, organisatiegegevens, facturen
ms.openlocfilehash: dad635df97e9cdf490118adc3a041c876878521b
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141326"
---
# <a name="understand-your-invoice"></a>Inzicht in uw factuur

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum verandert. Als uw ervaring niet overeenkomt met de hier gepresenteerde details, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

De factuur bevat een overzicht van uw kosten en betalingsinstructies. U [uw online factuur bekijken](#view-your-online-invoice) in het Microsoft 365-beheercentrum. U het ook downloaden in de Portable Document Format (.pdf) om te verzenden via e-mail.

Zie [Uw factuur voor Microsoft 365 voor Bedrijven begrijpen](understand-your-invoice2.md)als u alleen een Microsoft 365-abonnement hebt.

## <a name="understand-the-invoice-header"></a>De factuurkoptekst begrijpen

De bovenkant van de eerste pagina identificeert wie verantwoordelijk is voor de betaling, waar de factuur wordt verzonden, en een overzicht van kosten.

| Termijn | Beschrijving |
| --- | --- |
| Verkocht aan |Het factureringsaccount dat de naam en het adres van de rechtspersoon identificeert die verantwoordelijk is voor de betaling. Deze informatie kan worden beheerd op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Factureringsaccounts,</a> waar u de accountovereenkomst vinden en rollen en machtigingen beheren. |
| Bill aan |Hiermee wordt aangegeven wie de factuur ontvangt. Deze informatie kan worden beheerd op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Factureringsprofielen.</a> Het factureringsprofiel wordt ook weergegeven op de online factuurpagina in de sectie **Factuuroverzicht.** Zie [Factureringsprofielen beheren](manage-billing-profiles.md)voor meer informatie over factureringsprofielen en hoe u deze gebruiken om flexibelere factureringsopties voor uw organisatie op te bouwen. |
| Factureringsprofiel |De naam van het factureringsprofiel dat wordt gebruikt om factuureigenschappen zoals Factuur- en PO-nummer en betalingsvoorwaarden te definiëren. Deze informatie kan worden beheerd op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Factureringsprofielen.</a> Zie [Factureringsprofielen beheren](manage-billing-profiles.md)voor meer informatie over factureringsprofielen en hoe u deze gebruiken om flexibelere factureringsopties voor uw organisatie op te bouwen. |
| Factuurnummer |Een uniek, door Microsoft gegenereerd factuurnummer dat wordt gebruikt voor trackingdoeleinden. |
| Factuurdatum |Datum waarop de factuur wordt gegenereerd, meestal vijf tot twaalf dagen na het einde van de factureringscyclus. U uw factuurdatum controleren op de pagina met details van het factureringsprofiel. Kosten die plaatsvinden tussen het einde van de factureringsperiode en de factuurdatum worden opgenomen in de factuur voor de volgende maand, omdat ze zich in de volgende factureringsperiode bevinden. De begin- en einddatum van de factureringsperiode voor elke factuur worden weergegeven in de factuur-PDF boven **het factureringsoverzicht**.|
| Betalingsvoorwaarden |Hoe u betaalt voor uw Microsoft-factuur. *Netto 30 dagen* betekent dat u betaalt door instructies op uw factuur te volgen, binnen 30 dagen na de factuurdatum. |

## <a name="understand-the-billing-summary"></a>Inzicht in het factureringsoverzicht

In **het overzicht facturering** wordt het overzicht van de kosten sinds de vorige factureringsperiode weergegeven, eventuele credits die zijn toegepast, de belasting en het totale verschuldigde bedrag.

| Termijn | Beschrijving |
| --- | --- |
| Kosten|Totaal aantal producten dat voor deze factureringsperiode is gekocht en de bijbehorende kosten en belastingen. Aankopen worden samengevoegd om een beknopt overzicht van uw factuur te geven. |
| Tegoeden |Credits die je hebt ontvangen van retourzendingen |
| Azure-credits toegepast |Uw Azure-tegoeden die automatisch worden toegepast op Azure kosten elke factureringsperiode. Als u geen Azure-credits hebt, is dit veld verborgen. Zie [Azure-tegoed van Microsoft Customer Agreement voor](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance)meer informatie over Azure-tegoed . |
| Subtotaal |Het verschuldigde bedrag vóór belastingen |
| Belasting |Het type en het bedrag van de belasting die u betaalt, afhankelijk van het land van uw factureringsprofiel. Als u geen belasting hoeft te betalen, wordt er geen belasting weergegeven op uw factuur. |

### <a name="understand-your-charges"></a>Begrijp uw kosten

De kosten pagina's tonen de kosten uitgesplitst naar product. Voor Azure-klanten kunnen de kosten worden georganiseerd per factuursectie. Zie [Factuursecties](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections) in Aan de slag met uw [factureringsaccount voor Microsoft-klantenovereenkomst](https://docs.microsoft.com/azure/billing/billing-mca-overview)voor meer informatie over hoe factuursecties worden gebruikt met Azure-producten. Binnen elke productorder worden de kosten opgesplitst per servicefamilie.

| Termijn |Beschrijving |
| --- | --- |
| Eenheidsprijs | De effectieve eenheidsprijs van de service (in prijsvaluta) die wordt gebruikt om de kosten te berekenen. Deze prijs is uniek voor een product, servicefamilie, meter en aanbieding. |
| Veld | Aantal gekocht of verbruikt tijdens de factureringsperiode |
| Kosten/credits | Netto bedrag van de kosten na kredieten / terugbetalingen worden toegepast |
| Azure-tegoed | Het bedrag van Azure-tegoeden dat wordt toegepast op de kosten/credits |
| Belastingtarief | Belastingtarief, afhankelijk van het land |
| Belastingbedrag | Bedrag van de belasting toegepast op de aankoop op basis van belastingtarief |
| Totaal | Het totale bedrag dat verschuldigd is voor de aankoop |

De details van lijnartikelen zijn afhankelijk van het type product waarvoor u in rekening wordt gebracht. Voor Azure-producten wordt bijvoorbeeld de hoeveelheid toegepaste Azure-credits weergegeven. Producten op basis van zitplaatsen tonen een eenheidsprijs en -hoeveelheid. De factuurdetails geven een overzicht van de gekochte producten, kortingspunten of credits die zijn toegepast, het belastingtarief en het bedrag en de totalen van het regelartikel.

`Total = Charges - Azure Credit + Tax`

Het totale verschuldigde bedrag voor elke servicefamilie wordt berekend door Azure-tegoeden af te trekken van credits/kosten en belasting toe te voegen:

`Total = Charges/Credits - Azure Credit + Tax`

Zie Uw factuur voor de [microsoft-overeenkomst controleren](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill)als er Azure-kosten op uw factuur staan waarop u meer details wilt.

## <a name="understand-the-last-invoice-page"></a>De laatste factuurpagina begrijpen

### <a name="payment-instructions"></a>Betalingsinstructies

Onderaan de factuur staan instructies over het betalen van uw factuur. U betalen via draad, cheque of online.

### <a name="publisher-information"></a>Informatie over uitgevers

Als u services van derden in uw factuur hebt staan, staan de naam en het adres van elke uitgever onderaan uw factuur.

## <a name="view-your-online-invoice"></a>Uw online factuur bekijken

Facturen zijn online beschikbaar. Een link naar uw online factuur is beschikbaar via uw PDF-factuur en via een e-mailmelding. De online factuur is uitbreidbaar, zodat u de kosten op uw factuur bekijken en meer details voor elk artikel bekijken. De online factuur omvat:

- **Prijsdetails** &mdash; Aanvullende informatie, inclusief details over kortingen en productprijzen.

- **Online betalen** &mdash; U ervoor kiezen om online een betaling uit te voeren vanaf de factuur.

- **Azure-kostenbeheer** &mdash; Voor Azure-klanten bevatten online facturen een koppeling naar Azure-kostenbeheer.

### <a name="to-view-your-online-invoice"></a>Uw online factuur bekijken

1. Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturen en betalingen</a>.

2. Als u de .pdf-versie van uw factuur wilt downloaden, kiest u **Factuur-PDF downloaden** in de rij voor de factuur die u wilt zien.

3. Als u uw online factuur wilt bekijken, kiest u een factuur in de lijst. U de .pdf ook downloaden van de pagina factuurgegevens.

## <a name="need-help-contact-support"></a>Hulp nodig? Neem contact op met ondersteuning.

Als u vragen hebt of hulp nodig hebt bij uw Azure-tegoed, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">maakt u een ondersteuningsaanvraag met Azure-ondersteuning.</a>

Als u vragen hebt of hulp nodig hebt bij uw factuur in het Microsoft 365-beheercentrum, neemt u [contact op met de ondersteuning voor zakelijke producten.](../../admin/contact-support-for-business-products.md)
