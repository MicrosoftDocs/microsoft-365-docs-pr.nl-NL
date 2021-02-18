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
description: In dit artikel leert u hoe u de delist-portal gebruikt om uzelf te verwijderen uit de lijst met geblokkeerde afzenders in Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c11fced30ef52315ecb44dda51e6825d36b57c7e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287519"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>De delist-portal gebruiken om jezelf uit de lijst met geblokkeerde afzenders te verwijderen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Wordt er een foutbericht weergegeven wanneer u een e-mailbericht probeert te verzenden naar een geadresseerde van wie het e-mailadres zich in Microsoft 365 Als u denkt dat u het foutbericht niet moet ontvangen, kunt u de portal voor het verwijderen van uzelf uit de lijst met geblokkeerde afzenders verwijderen.

## <a name="what-is-the-blocked-senders-list"></a>Wat is de lijst met geblokkeerde afzenders?

Microsoft gebruikt de lijst met geblokkeerde afzenders om haar klanten te beschermen tegen spam, spoofing en phishing-aanvallen. Het IP-adres van uw e-mailserver, dat wil zeggen het adres dat door uw e-mailserver wordt gebruikt om zichzelf op internet te identificeren, is om een aantal redenen gelabeld als een mogelijke bedreiging voor Microsoft 365. Wanneer Microsoft 365 het IP-adres aan de lijst toevoegt, wordt alle communicatie tussen het IP-adres en onze klanten via onze datacenters voorkomen.

U weet dat u aan de lijst bent toegevoegd wanneer u een antwoord op een e-mailbericht ontvangt met een foutmelding die er als volgende uitziet:

> 550 5.7.606-649 Access geweigerd, verzenden van IP geweigerd [_IP-adres_]; Als u uit deze lijst wilt verwijderen, gaat u naar de aanwijzingen en <https://sender.office.com/> volgt u deze. Zie rapporten over [niet-bezorging van e-mail in Exchange Online voor meer informatie.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

waarbij  _IP-adres_ het IP-adres is van de computer waarop de e-mailserver wordt uitgevoerd.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Delist Portal gebruiken om uzelf te verwijderen uit de lijst met geblokkeerde afzenders

1. Ga in een webbrowser naar <https://sender.office.com> .

2. Volg de instructies op de pagina. Zorg ervoor dat u het e-mailadres gebruikt waar het foutbericht naar is verzonden en het IP-adres dat is opgegeven in het foutbericht. U kunt slechts één e-mailadres en één IP-adres per bezoek invoeren.

3. Klik **op Verzenden.**

    Via de portal wordt een e-mail verzonden naar het e-mailadres dat u oplevert. Het e-mailbericht ziet er dan als volgt uit: Schermafbeelding van de e-mail die wordt ontvangen wanneer u een ![ aanvraag indient via de delistportal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Klik op de bevestigingskoppeling in de e-mail die naar u is verzonden via de portal voor het in-/uiten.

    U gaat nu terug naar de portal voor het delisten.

5. Klik in de portal Delist op **IP delisten.**

    Nadat het IP-adres is verwijderd uit de lijst met geblokkeerde afzenders, worden e-mailberichten van dat IP-adres bezorgd bij geadresseerden die Microsoft 365 gebruiken. Zorg er dus voor dat u zeker weet dat e-mail die vanaf dat IP-adres wordt verzonden, niet aanstootgevend of schadelijk zal zijn. anders wordt het IP-adres mogelijk opnieuw geblokkeerd.

    > [!NOTE]
    > Het kan tot 24 uur duren of de resultaten kunnen sterk variëren voordat de beperkingen worden verwijderd.

Zie [Lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md) en uitgaande [spambeveiliging in EOP](outbound-spam-controls.md) om te voorkomen dat een IP wordt geblokkeerd.
