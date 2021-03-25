---
title: Uzelf verwijderen uit de lijst met geblokkeerde afzenders
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u de portal voor het verwijderen van lijsten kunt gebruiken om uzelf te verwijderen uit de lijst met geblokkeerde afzenders van Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4488f5e5607d71da35b2921e863fb02195467e2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204445"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>De delist-portal gebruiken om jezelf uit de lijst met geblokkeerde afzenders te verwijderen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Krijgt u een foutbericht wanneer u een e-mailbericht probeert te verzenden naar een geadresseerde van wie het e-mailadres zich in Microsoft 365? Als u denkt dat u het foutbericht niet moet ontvangen, kunt u de portal voor het verwijderen van de lijst met geblokkeerde afzenders gebruiken.

## <a name="what-is-the-blocked-senders-list"></a>Wat is de lijst met geblokkeerde afzenders?

Microsoft gebruikt de lijst met geblokkeerde afzenders om haar klanten te beschermen tegen spam-, spoofing- en phishingaanvallen. Het IP-adres van uw e-mailserver, dat wil zeggen het adres dat uw e-mailserver gebruikt om zich op internet te identificeren, is om verschillende redenen gelabeld als een mogelijke bedreiging voor Microsoft 365. Wanneer Microsoft 365 het IP-adres aan de lijst toevoegt, wordt alle verdere communicatie tussen het IP-adres en een van onze klanten via onze datacenters voorkomen.

U weet dat u aan de lijst bent toegevoegd wanneer u een antwoord ontvangt op een e-mailbericht met een fout die er zo uitziet:

> 550 5.7.606-649 Access geweigerd, ip-adres verzenden verboden [_IP-adres_]; Als u verwijdering uit deze lijst wilt aanvragen, gaat u naar <https://sender.office.com/> de routebeschrijving en volgt u deze. Zie Rapporten over [niet-bezorgde e-mail in Exchange Online voor meer informatie.](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

waarbij  _IP-adres_ het IP-adres is van de computer waarop de e-mailserver wordt uitgevoerd.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Delist portal gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen

1. Ga in een webbrowser naar <https://sender.office.com> .

2. Volg de instructies op de pagina. Zorg ervoor dat u het e-mailadres gebruikt waarop het foutbericht is verzonden en het IP-adres dat is opgegeven in het foutbericht. U kunt slechts één e-mailadres en één IP-adres per bezoek invoeren.

3. Klik **op Verzenden.**

    De portal stuurt een e-mail naar het e-mailadres dat u oplevert. De e-mail ziet er als volgt uit: Schermafbeelding van e-mail die is ontvangen wanneer u een aanvraag indient ![ via de delistportal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Klik op de bevestigingskoppeling in de e-mail die naar u is verzonden via de portal voor het op de lijst zetten.

    Hiermee gaat u terug naar de portal voor het op de lijst zetten.

5. Klik in de lijstportal op **IP-lijst delisten.**

    Nadat het IP-adres is verwijderd uit de lijst met geblokkeerde afzenders, worden e-mailberichten van dat IP-adres bezorgd bij geadresseerden die Microsoft 365 gebruiken. Zorg er dus voor dat u er zeker van bent dat e-mail die vanaf dat IP-adres wordt verzonden, niet aanstootgevend of schadelijk is. anders wordt het IP-adres mogelijk opnieuw geblokkeerd.

    > [!NOTE]
    > Het kan tot 24 uur duren of de resultaten kunnen sterk variëren voordat beperkingen worden verwijderd.

Zie [Lijsten met veilige afzenders maken in EOP-](create-safe-sender-lists-in-office-365.md) en Uitgaande [spambeveiliging in EOP](outbound-spam-controls.md) om te voorkomen dat een IP-adres wordt geblokkeerd.