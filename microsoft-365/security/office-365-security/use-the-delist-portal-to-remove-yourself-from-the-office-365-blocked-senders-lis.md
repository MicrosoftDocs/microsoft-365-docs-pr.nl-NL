---
title: Gebruik de lijstportal om uzelf uit de lijst met geblokkeerde afzenders te verwijderen
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
description: Krijgt u een foutmelding wanneer u een e-mail probeert te verzenden naar een ontvanger wiens e-mailadres zich in Microsoft 365 bevindt? Als u denkt dat u het foutbericht niet moet ontvangen, u de lijst met de lijst gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen.
ms.openlocfilehash: 39f2c9335f162f26e8bf07a213236e0e0eefef2a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636402"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Gebruik de lijstportal om uzelf uit de lijst met geblokkeerde afzenders te verwijderen

Krijgt u een foutmelding wanneer u een e-mail probeert te verzenden naar een ontvanger wiens e-mailadres zich in Microsoft 365 bevindt? Als u denkt dat u het foutbericht niet moet ontvangen, u de lijst met de lijst gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen.

## <a name="what-is-the-blocked-senders-list"></a>Wat is de lijst met geblokkeerde afzenders?

Microsoft gebruikt de lijst met geblokkeerde afzenders om zijn klanten te beschermen tegen spam, spoofing en phishing-aanvallen. Het IP-adres van uw e-mailserver, dat wil zeggen het adres dat uw mailserver gebruikt om zich op internet te identificeren, is om verschillende redenen gelabeld als een potentiële bedreiging voor Microsoft 365. Wanneer Microsoft 365 het IP-adres aan de lijst toevoegt, voorkomt het elke verdere communicatie tussen het IP-adres en een van onze klanten via onze datacenters.

U weet dat u aan de lijst bent toegevoegd wanneer u een antwoord ontvangt op een e-mailbericht met een foutmelding die een fout bevat die er ongeveer als volgt uitziet:

> 550 5.7.606-649 Toegang geweigerd, verboden verzenden IP [_IP-adres_]; Om verwijdering uit deze https://sender.office.com/ lijst aan te vragen, u de aanwijzingen bezoeken en volgen. Zie Rapporten [voor niet-bezorging e-mailen in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

waar _IP-adres_ het IP-adres is van de computer waarop de e-mailserver wordt uitgevoerd.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Delijstportal gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen

1. Ga in een webbrowser [https://sender.office.com](https://sender.office.com)naar .

2. Volg de instructies op de pagina. Controleer of u het e-mailadres gebruikt waarnaar het foutbericht is verzonden en het IP-adres dat is opgegeven in het foutbericht. U slechts één e-mailadres en één IP-adres per bezoek invoeren.

3. Klik **op Verzenden**.

    De portal stuurt een e-mail naar het e-mailadres dat u verstrekt. De e-mail ziet er ![ongeveer als volgt uit: Screenshot van e-mail ontvangen wanneer u een verzoek indient via de lijst portal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Klik op de bevestigingskoppeling in de e-mail die u door de niet-vermeldende portal is verzonden.

    Dit brengt je terug naar de lijst portaal.

5. Klik in de lijstportal op **Ip van de lijst schrappen**.

    Nadat het IP-adres uit de lijst met geblokkeerde afzenders is verwijderd, worden e-mailberichten van dat IP-adres bezorgd aan ontvangers die Microsoft 365 gebruiken. Zorg er dus voor dat e-mail die vanaf dat IP-adres wordt verzonden, niet beledigend of kwaadaardig is. anders kan het IP-adres opnieuw worden geblokkeerd.

    > [!NOTE]
    > Het kan tot 24 uur duren of de resultaten kunnen sterk variëren voordat beperkingen worden verwijderd.

Zie [Lijsten met veilige afzenders maken in Office 365](create-safe-sender-lists-in-office-365.md) en Uitgaande [spambeveiliging in Office 365](outbound-spam-controls.md) om te voorkomen dat IP op de zwarte lijst komt te staan.
