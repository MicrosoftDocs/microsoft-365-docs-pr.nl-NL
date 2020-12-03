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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u de lijst Portal kunt gebruiken om uzelf te verwijderen uit de lijst met geblokkeerde afzenders in Microsoft 365.
ms.openlocfilehash: f4e7bcc13ac6c133880eb0ebe69ba3f724d0a84e
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561421"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>De delist-portal gebruiken om jezelf uit de lijst met geblokkeerde afzenders te verwijderen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Wordt er een foutbericht weergegeven wanneer u probeert een e-mailbericht te verzenden naar een geadresseerde waarvan het e-mailadres zich in Microsoft 365 bevindt? Als u denkt dat het foutbericht moet worden weergegeven, kunt u de lijst met geblokkeerde afzenders gebruiken om uzelf te verwijderen uit de lijst met geblokkeerde afzenders.

## <a name="what-is-the-blocked-senders-list"></a>Wat is de lijst met geblokkeerde afzenders?

Microsoft gebruikt de lijst met geblokkeerde afzenders om klanten tegen spam, spoofing en phishing-aanvallen te beschermen. Het IP-adres van uw e-mailserver, dat wil zeggen het adres dat door uw e-mailserver wordt gebruikt om zichzelf te identificeren op internet, is als mogelijke bedreiging voor Microsoft 365 in een van de verschillende redenen. Wanneer Microsoft 365 het IP-adres aan de lijst toevoegt, voorkomt u dat alle verdere communicatie tussen het IP-adres en een van onze klanten via onze datacenters wordt toegevoegd.

U weet dat u bent toegevoegd aan de lijst wanneer u een antwoord ontvangt voor een e-mailbericht met een foutmelding die er ongeveer als volgt uitziet:

> 550 5.7.606-649 toegang geweigerd, weigering IP [_IP Address_]; Als u het verwijderen van deze lijst wilt aanvragen, gaat u <https://sender.office.com/> verder met de instructies. Zie [rapporten over niet-uitgevoerde bezorging van e-mail in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)voor meer informatie.

waarbij  _IP-adres_ het IP-adres is van de computer waarop de e-mailserver wordt uitgevoerd.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>U kunt als volgt de lijst met geblokkeerde afzenders gebruiken om de portal te verwijderen

1. Ga in een webbrowser naar <https://sender.office.com> .

2. Volg de instructies op de pagina. Zorg ervoor dat u het e-mailadres gebruikt waarnaar het foutbericht is verzonden en het IP-adres dat is opgegeven in het foutbericht. U kunt slechts één e-mailadres en één IP-adres per bezoek invoeren.

3. Klik op **verzenden**.

    De portal verzendt een e-mailadres naar het e-mailadres dat u opgeeft. Het e-mailbericht ziet er ongeveer als volgt ![ uit: schermafbeelding van een e-mailbericht dat u ontvangt wanneer u een aanvraag indient via de portal voor delistren](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Klik op de bevestigings koppeling in het e-mailbericht dat naar u is verzonden, via de portal voor het opzeggen van de portal.

    U gaat terug naar de lijst Portal.

5. Klik in het vak Portal delijstte op **IP-adres weergeven**.

    Nadat het IP-adres is verwijderd uit de lijst met geblokkeerde afzenders, worden e-mailberichten van dat IP-adres afgeleverd bij geadresseerden die gebruikmaken van Microsoft 365. Zorg ervoor dat het e-mailadres dat via dat IP-adres is verzonden, niet beledigend of schadelijk kan zijn. anders wordt het IP-adres mogelijk opnieuw geblokkeerd.

    > [!NOTE]
    > Het kan tot 24 uur duren voordat de beperkingen worden verwijderd.

Zie [voor meer informatie over het maken van lijsten met veilige afzenders in EOP](create-safe-sender-lists-in-office-365.md) en [uitgaande spam bescherming in EOP](outbound-spam-controls.md) om te voorkomen dat een IP wordt geblokkeerd.
