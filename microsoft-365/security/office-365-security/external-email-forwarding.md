---
title: Externe e-mailberichten configureren en beheren, automatisch doorsturen, 5.7.520 toegang geweigerd, externe forwarding uitschakelen, de beheerder heeft extern doorsturen uitgeschakeld, beleid voor uitgaand Antispambeleid
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
ms.openlocfilehash: 727f14e8158f7e024b6029231fed18adb2d56a62
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949682"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>Externe e-mail forwarding configureren in Office 365

Extern doorsturen wordt bepaald door het *uitgaande Antispambeleid* en de reikwijdte van de gebruikers op basis van de geconfigureerde instelling. Momenteel worden de instellingen voor 3 weer geboden:

- **Automatisch** : in deze modus is het systeem verantwoordelijk voor het bepalen of een doorgestuurd bericht wel of niet is toegestaan.  Dit is de standaardmodus en in deze modus wordt het automatisch extern doorsturen van het systeem blokkeren.

- **On** -automatisch extern doorsturen is toegestaan en niet beperkt.

- **Uitgeschakeld** – automatisch extern doorsturen is uitgeschakeld en resulteert in een rapport over niet-uitgevoerde bezorging (NDR) voor de eindgebruiker.

Zie [uitgaande spamfilters configureren in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) voor meer informatie over het configureren van deze instellingen.

> [!NOTE]
> Als u automatisch doorsturen uitschakelt, worden ook regels voor het postvak in van berichten naar externe adressen dsable.

## <a name="controlling-external-email-forwarding"></a>Externe e-mail doorsturen beheren

Als beheerder van een organisatie hebt u mogelijk de mogelijkheid om te bepalen welke e-mailberichten automatisch kunnen worden doorgestuurd met behulp van regels voor Postvak in of het doorsturen van SMTP, buiten de organisatie. Het doorsturen van e-mail kan een handige functie zijn, maar kan ook een risico vormen via de potentiële informatie informatie, zelfs door informatie te verstrekken aan kwaadwillende gebruikers die kunnen worden gebruikt om de organisatie of haar partners te bezorgen.

In Office 365 is automatisch extern doorsturen niet toegestaan door regels voor Postvak in of de configuratie van het e-mailbericht, dat een veilig standaardbeleid biedt. De beheerder kan deze instellingen echter wijzigen voor alle gebruikers in de organisatie. Het doorsturen van berichten tussen interne gebruikers wordt niet beïnvloed door een wijziging.

> [!NOTE]
> Als u automatisch doorsturen naar externe adressen in Office 365 uitschakelt, wordt deze uitgerold in fasen met details die zijn gecommuniceerd via berichten in het [berichtencentrum](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) . Om te voorkomen dat deze wijzigingen door de beheerder worden voorgezet, kunnen ze beleidsregels op een juiste moment wijzigen om ervoor te zorgen dat hun gebruikers geen onderbrekingen hebben.

Meer informatie over gebruikers die automatisch doorsturen (regels voor Postvak in of het doorsturen van e-mail) in uw organisatie worden gebruikt, vindt u in het [rapport automatisch doorgestuurde berichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a>Hoe werkt dit beleid met andere besturingselementen voor automatisch doorsturen

Als beheerder hebt u mogelijk al een ander typebesturingselement ter plaatse, zodat het automatisch doorsturen in [externe domeinen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) en het gebruik van een ETR toe (Exchange-Transport regel) wordt geblokkeerd. Beide besturingselementen zijn niet van toepassing op deze specifieke functie, bijvoorbeeld als u automatisch doorsturen wilt toestaan voor een extern domein, maar automatisch doorsturen wilt blokkeren via het uitgaande spam beleid. Ook als u automatisch doorsturen in het beleid voor uitgaande spam toestaat maar dit blokkeert in een ETR toe of een extern domein, wordt het bericht geblokkeerd door een van deze besturingselementen. U kunt bijvoorbeeld automatisch doorsturen in het beleid voor uitgaande spam toestaan en externe domeinen gebruiken om te bepalen met welke domeinen gebruikers automatisch berichten kunnen doorsturen.


## <a name="the-blocked-email-forwarding-message"></a>Bericht met doorsturen van geblokkeerde e-mail

Wanneer een bericht wordt weergegeven als automatisch doorgeschakeld en het organisatiebeleid *blokkeert* deze activiteit, wordt een **NDR-rapport (Non-Delivery Report)** weergegeven voor de eindgebruiker. In het rapport wordt aangegeven dat het bericht niet is afgeleverd. De NDR heeft de volgende indeling: 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
