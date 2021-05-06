---
title: E-mailthreading in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Bij het uitvoeren Advanced eDiscovery een e-mailthreading een e-mailgesprek parseert en elk bericht in verschillende categorieën scheidt.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161533"
---
# <a name="email-threading-in-advanced-ediscovery"></a>E-mailthreading in Advanced eDiscovery

Overweeg een e-mailgesprek dat al een tijdje gaande is. In de meeste gevallen bevat de laatste e-mail in de thread de inhoud van alle voorgaande e-mailberichten. Als u de laatste e-mail bekijkt, krijgt u een volledige context van het gesprek dat in de thread is gebeurd. E-mailthreading identificeert dergelijke e-mailberichten, zodat revisoren een deel van de verzamelde documenten kunnen bekijken zonder context te verliezen.

## <a name="what-does-email-threading-do"></a>Wat doet e-mailthreading?

E-mailthreading parseert elke e-mail en deconstrueert deze naar afzonderlijke berichten; elke e-mail is een keten van afzonderlijke berichten. Vervolgens worden alle e-mailberichten in de revisieset geanalyseerd om te bepalen of een e-mail unieke inhoud heeft of dat de keten volledig in een andere e-mail is opgenomen. Uiteindelijk zijn e-mailberichten onderverdeeld in vier categorieën:

- **Inclusief:** het laatste bericht in de e-mail bevat unieke inhoud en de e-mail bevat alle bijlagen die zijn opgenomen in andere e-mailberichten waarvan de inhoud volledig in deze e-mail is opgenomen.

- **Inclusief min:** het laatste bericht in de e-mail bevat unieke inhoud, maar de e-mail bevat geen enkele van de bijlagen die zijn opgenomen in andere e-mailberichten waarvan de inhoud volledig in deze e-mail is opgenomen.

- **Inclusief exemplaar:** een exacte kopie van een inclusief/inclusief min-e-mailbericht

- **Geen:** De inhoud van dit e-mailbericht bevat ten minste één e-mailbericht dat is gemarkeerd als inclusief/inclusief min.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>Hoe verschilt dit van gesprekken in Outlook?

In één oogopslag klinkt dit vergelijkbaar met gespreksgroeperingen in Outlook. Er zijn echter enkele belangrijke verschillen. Overweeg een e-mailgesprek dat in twee gesprekken is gevorkt; Iemand heeft bijvoorbeeld gereageerd op een e-mailbericht dat niet de laatste is in het gesprek, zodat de laatste twee e-mailberichten in het gesprek unieke inhoud hebben.

Outlook zou de e-mailberichten nog steeds in één gesprek groeperen. als u alleen de laatste e-mail leest, ontbreekt de context van het een-na-laatste e-mailbericht, dat ook unieke inhoud bevat. Omdat e-mailthreading elke e-mail in afzonderlijke onderdelen parseert en vergelijkt, worden beide laatste twee e-mailberichten door e-mailthreading gemarkeerd als inclusief, zodat u geen context mist zolang u alle e-mailberichten leest die als inclusief zijn gemarkeerd.
