---
title: Externe e-mail doorsturen configureren en beheren, Automatisch doorsturen, 5.7.520 Access Denied, uitschakelen van extern doorsturen, Uw beheerder heeft extern doorsturen uitgeschakeld, uitgaand antispambeleid
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080111"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>Externe e-mail doorsturen configureren in Office 365

Extern doorsturen wordt beheerd door het *uitgaande antispambeleid* en scoped naar gebruikers op basis van de geconfigureerde instelling. Momenteel worden 3 instellingen ondersteund:

- **Automatisch** - In deze modus is het systeem verantwoordelijk voor de beslissing of een doorgestuurd bericht is toegestaan of niet.  Dit is de standaardmodus en in deze modus blokkeert het systeem automatisch extern doorsturen.

- **Aan** – Automatisch extern doorsturen is toegestaan en niet beperkt.

- **Uit** - Automatisch extern doorsturen is uitgeschakeld en resulteert in een Non-delivery report (NDR) aan de eindgebruiker.

Zie [Uitgaande spamfiltering configureren in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) voor meer informatie over het configureren van deze instellingen.

## <a name="controlling-external-email-forwarding"></a>Externe e-mail doorsturen beheren

Als beheerder van een organisatie u bedrijfsvereisten hebben om te beperken of te bepalen wie e-mails automatisch kan doorsturen met behulp van inboxregels of SMTP-doorsturen buiten de organisatie. E-mail doorsturen kan een nuttige functie zijn, maar kan ook een risico vormen door de mogelijke openbaarmaking van informatie, zelfs door het verstrekken van informatie aan aanvallers die kunnen worden gebruikt om de organisatie of haar partners aan te vallen.

Office 365 staat geen automatische externe doorschakeling toe via inboxregels of postvakconfiguratie, wat een veilig standaardbeleid biedt. De beheerder kan deze instellingen echter wijzigen voor alle of sommige gebruikers in de organisatie. Het doorsturen van berichten tussen interne gebruikers wordt niet beïnvloed door een dergelijke wijziging.

> [!NOTE]
> Het uitschakelen van automatisch doorsturen naar externe adressen in Office 365 wordt gefaseerd uitgerold, waarbij details worden gecommuniceerd via [berichten in het Berichtencentrum.](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) Om beheerders te helpen zich voor te bereiden op deze wijzigingen, moet u het beleid van tevoren wijzigen om ervoor te zorgen dat er geen verstoring is voor hun gebruikers.

Meer informatie over gebruikers die automatisch doorsturen gebruiken (regels voor inbox of SMTP-doorsturen) in uw organisatie, vindt u in het [rapport automatisch doorgestuurde berichten.](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide)

## <a name="the-blocked-email-forwarding-message"></a>Het geblokkeerde e-mailbericht

Wanneer een bericht wordt gedetecteerd als automatisch doorgestuurd en het organisatiebeleid *blokkeert* dat de activiteit een **Non-delivery rapport (NDR)** zal worden gegenereerd terug naar de eindgebruiker. Het rapport geeft aan dat het bericht niet is bezorgd. De NDR heeft de volgende indeling: 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
