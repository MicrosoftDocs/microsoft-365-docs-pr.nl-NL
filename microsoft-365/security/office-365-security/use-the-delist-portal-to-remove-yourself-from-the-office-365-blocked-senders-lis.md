---
title: Verwijder jezelf uit de lijst met geblokkeerde afzenders
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
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u de verwijderingsportal gebruiken om uzelf uit de lijst met geblokkeerde afzenders van Microsoft 365 te verwijderen.
ms.openlocfilehash: 2d9dbba12740e62305e1bcfd193175659be34026
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739241"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>De delist-portal gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen

Krijgt u een foutmelding wanneer u een e-mail probeert te sturen naar een ontvanger wiens e-mailadres in Microsoft 365 staat? Als u denkt dat u het foutbericht niet moet ontvangen, u de pagina verwijderen om uzelf uit de lijst met geblokkeerde afzenders te verwijderen.

## <a name="what-is-the-blocked-senders-list"></a>Wat is de lijst met geblokkeerde afzenders?

Microsoft gebruikt de lijst met geblokkeerde afzenders om zijn klanten te beschermen tegen spam-, spoofing- en phishing-aanvallen. Het IP-adres van uw e-mailserver, dat wil zeggen het adres dat uw e-mailserver gebruikt om zich op internet te identificeren, is om verschillende redenen getagd als een potentiële bedreiging voor Microsoft 365. Wanneer Microsoft 365 het IP-adres aan de lijst toevoegt, voorkomt dit alle verdere communicatie tussen het IP-adres en een van onze klanten via onze datacenters.

U weet dat u aan de lijst bent toegevoegd wanneer u een antwoord op een e-mailbericht ontvangt met een fout die er ongeveer als volgt uitziet:

> 550 5.7.606-649 Access geweigerd, verboden verzenden van IP [_IP-adres_]; Om verwijdering van deze lijst aan te vragen, u https://sender.office.com/ terecht op de aanwijzingen en de aanwijzingen volgen. Zie Rapporten [over niet-levering e-mailen in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)voor meer informatie.

waarbij _IP-adres_ het IP-adres is van de computer waarop de e-mailserver wordt uitgevoerd.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Delist-portal gebruiken om uzelf uit de lijst met geblokkeerde afzenders te verwijderen

1. Ga in een webbrowser naar [https://sender.office.com](https://sender.office.com) .

2. Volg de instructies op de pagina. Zorg ervoor dat u het e-mailadres gebruikt waarop het foutbericht is verzonden en het IP-adres dat is opgegeven in het foutbericht. U slechts één e-mailadres en één IP-adres per bezoek invoeren.

3. Klik **op Verzenden**.

    De portal stuurt een e-mail naar het e-mailadres dat u aangeeft. De e-mail ziet er ongeveer als volgt uit: ![ Schermafbeelding van ontvangen e-mail wanneer u een verzoek indient via de schrappingsportaal](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Klik op de bevestigingslink in de e-mail die u door de schrappingsportal is verzonden.

    Dit brengt je terug naar de schrappingsportaal.

5. Klik in de schrappingsportal op **IP schrappen**.

    Nadat het IP-adres uit de lijst met geblokkeerde afzenders is verwijderd, worden e-mailberichten van dat IP-adres bezorgd aan ontvangers die Microsoft 365 gebruiken. Zorg er dus voor dat je er zeker van bent dat e-mail die vanaf dat IP-adres wordt verzonden, niet beledigend of kwaadaardig is; anders kan het IP-adres opnieuw worden geblokkeerd.

    > [!NOTE]
    > Het kan tot 24 uur duren of de resultaten kunnen sterk variëren voordat beperkingen worden verwijderd.

[Zie Veilige afzenderlijsten maken in EOP-](create-safe-sender-lists-in-office-365.md) en [Uitgaande spambeveiliging in EOP](outbound-spam-controls.md) om te voorkomen dat een IP-adres wordt geblokkeerd.
