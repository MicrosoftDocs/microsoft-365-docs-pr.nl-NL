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
ms.openlocfilehash: c0a3849d330b508630eb60c7ee24cd8b498a32b8
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417227"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>Externe e-mail forwarding configureren in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Extern doorsturen wordt bepaald door het *uitgaande Antispambeleid* en de reikwijdte van de gebruikers op basis van de geconfigureerde instelling. Momenteel worden de instellingen voor 3 weer geboden:

- **Automatisch** – dit is door het systeem beheerde functies: uitgaande spamfilters om automatisch externe e-mailberichten te kunnen doorsturen. Dit is de standaardinstelling.

- **On** -automatisch extern doorsturen is toegestaan en niet beperkt.

- **Uitgeschakeld** – automatisch extern doorsturen is uitgeschakeld en resulteert in een rapport over niet-uitgevoerde bezorging (NDR) voor de eindgebruiker.

Zie [uitgaande spamfilters configureren in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) voor meer informatie over het configureren van deze instellingen.

> [!NOTE]
> Als u automatisch doorsturen uitschakelt, worden ook regels voor het postvak in uitgeschakeld waarmee berichten naar externe adressen worden doorgestuurd.

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
