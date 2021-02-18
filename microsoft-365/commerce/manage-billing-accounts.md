---
title: Factureringsaccounts beheren
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Meer informatie over factureringsaccounts en hoe u deze kunt beheren.
ms.openlocfilehash: 6c90bdd9087a67cc3639cfb06644a5587273dc35
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279296"
---
# <a name="manage-billing-accounts"></a>Factureringsaccounts beheren

Er wordt een factureringsaccount gemaakt wanneer u zich registreert om Microsoft-producten te proberen of kopen. U gebruikt uw factureringsaccount om uw accountinstellingen, facturen, betalingsmethoden en aankopen te beheren. U kunt toegang hebben tot meerdere factureringsaccounts. U hebt zich bijvoorbeeld rechtstreeks aangemeld voor Microsoft 365 of u hebt toegang tot de Enterprise Agreement, de Microsoft &-servicesovereenkomst of de Microsoft-klantovereenkomst van uw organisatie. Voor elk van deze scenario's hebt u een apart factureringsaccount.

Het Microsoft 365-beheercentrum ondersteunt momenteel het volgende type factureringsaccounts:

- Microsoft Online Services-programma: Dit factureringsaccount wordt gemaakt wanneer u zich rechtstreeks voor een Microsoft 365-abonnement registreert.
- Microsoft Products & Services Agreement (MPSA) Program: Dit factureringsaccount wordt gemaakt wanneer uw organisatie een MPSA Volume Licensing-overeenkomst voor het aanschaffen van software en onlineservices ondertekent.
- Microsoft-klantovereenkomst: Dit factureringsaccount wordt gemaakt wanneer je organisatie werkt met een Microsoft-vertegenwoordiger, een geautoriseerde partner of aankopen onafhankelijk van elkaar.

De <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">pagina Factureringsaccounts</a> biedt een weergave van uw commerciële accounts bij Microsoft. Uw organisatie heeft standaard ten minste één factureringsaccount gekoppeld aan een overeenkomst die wordt geaccepteerd op het moment van een directe aankoop, of via een volumelicentierangschikking.

## <a name="understand-billing-account-details"></a>Meer informatie over factureringsaccountgegevens

De bovenkant van de **detailpagina Factureringsaccounts** is uw accountprofiel en bevat juridische en belastinggegevens over uw organisatie. U kunt uw profiel bijwerken om uw wettelijke adres en telefoonnummer te wijzigen. Dit account is de rechtspersoon die de producten betaalt die u aanschaft.

De volgende tabel bevat de belangrijke termen die u ziet op de **detailpagina factureringsaccounts.**

| Veldnaam | Beschrijving |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Verkocht adres | De rechtspersoon die verantwoordelijk is voor de betaling en die is geïdentificeerd op de factuur. Het hier opgegeven adres wordt gebruikt om het belastingtarief vast te stellen, tenzij je tijdens je aankoop een alternatief verzendadres opgeeft. Bekijk [Belastinginformatie](billing-and-payments/tax-information.md) voor meer informatie. |
| Segment | Een alleen-lezenveld dat het zakelijke segment van uw organisatie aangeeft (Commercieel, Onderwijs, Overheid of Non-profit). |
| Accountstatus | Een alleen-lezenveld dat de status van uw commerciële account bij Microsoft aangeeft. |
| Belasting-id | Als u niet in de Verenigde Staten bent, moet u een btw- of lokaal equivalent geven. Bekijk [Belastinginformatie](billing-and-payments/tax-information.md) voor meer informatie. |
| Overeenkomst | Wanneer een factureringsaccount wordt gemaakt via een directe aankoop of een volumelicentieschikking, accepteert of ondertekent een ondertekenaar voor de organisatie een overeenkomst met een overzicht van de voorwaarden & het account. Indien van toepassing bevat deze weergave een overeenkomstgeschiedenis. Als u moet akkoord gaan met bijgewerkte voorwaarden, wordt een koppeling **naar** de overeenkomst voor Goedkeuren weergegeven. |
| Factureringsprofielen | Een factureringsprofiel definieert eigenschappen van uw factuur, zoals wie de factuur ontvangt, hoe de factuur wordt geleverd, betalingsvoorwaarden en een IO-nummer. Als u facturering wilt distribueren binnen uw organisatie, kunt u meerdere factureringsprofielen maken en het juiste factureringsprofiel identificeren op het moment van aankoop. Voor meer informatie over factureringsprofielen en hoe u ze kunt gebruiken om flexibelere factureringsopties voor uw organisatie te bouwen, begrijpt [u de factureringsprofielen.](billing-and-payments/manage-billing-profiles.md) |

> [!NOTE]
> Als u de  naam of het adres onder Verkocht moet  wijzigen, maar de koppeling Bewerken niet ziet, moet u [contact](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products) opnemen met ondersteuning om deze te wijzigen. Voor aanvragen voor **een wijziging van de naam Verkocht** aan is een kredietcontrole vereist. Vul [dit formulier in](https://www.microsoft.com/download/details.aspx?id=102732)en deel een van de volgende documenten met Microsoft wanneer u contact op kunt nemen met ondersteuning:
>
> - Door de overheid uitgegeven document of registratiebrief
> - Afdrukken in het register van het lokale bedrijf
>
> Ondersteuning kan helpen bij naam- en adreswijzigingen waarbij alleen de naam van de klant verandert, maar de entiteit blijft hetzelfde. In de documentatie moet duidelijk worden aangegeven dat alleen de naam van de entiteit is gewijzigd. Neem contact op met uw Microsoft-verkoper als de wijziging het resultaat is van een transactie, inclusief de verkoop van een bedrijf, een wijziging van de controle, of een verkooptransactie of een "spinoff" van een gelieerde klant.

## <a name="shipping-addresses"></a>Verzendadressen

In deze sectie worden de verzendadressen vermeld die zijn gekoppeld aan uw factureringsaccount. Wanneer u een aankoop doet, kunt u dit adres gebruiken om te bepalen waar uw aankoop is verzonden of gebruikt. Het verzendadres kan worden bewerkt. U kunt een verzendadres toevoegen of het bestaande adres bijwerken. Dit adres wordt gebruikt om het btw-tarief voor uw aankoop te bepalen.

## <a name="understand-access-to-billing-accounts"></a>Informatie over toegang tot factureringsaccounts

U kunt anderen toegang geven tot het factureringsaccount in het Microsoft 365-beheercentrum via rollen en machtigingen. Alleen de eigenaar van een factureringsaccount kan toegang tot een factureringsaccount verlenen. U kunt een van de volgende rollen toewijzen aan gebruikers:

- **Eigenaar factureringsaccount** &mdash; Kan machtigingen toewijzen, accounts bewerken, overeenkomsten ondertekenen en accounts weergeven.
- **Medewerker factureringsaccount** &mdash; Kan accounts bewerken, overeenkomsten ondertekenen en accounts weergeven.
- **Lezer van factureringsaccount** &mdash; Kan accounts weergeven.

> [!Note]
> Rollen voor factureringsaccounts zijn alleen van toepassing op factureringsaccounts en niet op andere scenario's in het Microsoft 365-beheercentrum.

## <a name="related-content"></a>Verwante onderwerpen

[Belastinginformatie](billing-and-payments/tax-information.md) (artikel) \
[Informatie over factureringsprofielen](billing-and-payments/manage-billing-profiles.md) (artikel)