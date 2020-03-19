---
title: Herstelacties in geautomatiseerd onderzoek en respons van Office 365
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, reactie, sanering, bedreigingen, geavanceerd, bedreiging, bescherming
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Meer informatie over herstelacties in geautomatiseerde onderzoeks- en responsmogelijkheden in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 2efe0124304a9f9dcfdc92b548c850882ad507a0
ms.sourcegitcommit: 841c06a5d566d404c35d5e9c0c7de5088daab976
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/18/2020
ms.locfileid: "42836856"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Herstelacties na een geautomatiseerd onderzoek in Office 365

## <a name="remediation-actions"></a>Saneringsacties

[Geautomatiseerde onderzoeks- en responsmogelijkheden](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 bevatten bepaalde herstelacties. Wanneer een geautomatiseerd onderzoek wordt uitgevoerd of is voltooid, ziet u meestal een of meer herstelacties waarvoor goedkeuring vereist is door uw beveiligingsteam om door te gaan. 

In de volgende tabel wordt een overzicht gemaakt van de herstelacties die momenteel beschikbaar zijn in Office 365 ATP. 

|Actie | Beschrijving |
|-----|-----|
|URL blokkeren (tijd van klikken) |Beschermt tegen e-mailberichten en documenten die kwaadaardige URL's bevatten. Dit maakt het blokkeren van schadelijke koppelingen en gerelateerde webpagina's via [veilige links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) mogelijk wanneer de gebruiker op een koppeling in een bestaand Office-bestand of in een ouder e-mailbericht klikt. |
|E-mail voor soft delete  |Verwijder zachte e-mailberichten uit het postvak van een gebruiker. <br/>Een bericht met zachte verwijderden wordt verplaatst naar de map Herstelbare items van een gebruiker en wordt behouden totdat de bewaartermijn voor verwijderde items is verstreken. |
|E-mailclusters voor soft delete  |Soft verwijdert schadelijke e-mailberichten die overeenkomen met een query uit de mailboxen van alle gebruikers. <br/>Zachte verwijderde berichten worden verplaatst naar de map Herstelbare items van gebruikers en worden bewaard totdat de bewaartermijn voor verwijderde items is verstreken. |
|Externe e-mail doorsturen uitschakelen |Hiermee verwijdert u een doorstuurregel uit het postvak van een specifieke eindgebruiker.|

> [!NOTE]
> In Office 365 ATP worden geen herstelacties automatisch uitgevoerd. Herstelacties worden alleen uitgevoerd na goedkeuring door het beveiligingsteam van uw organisatie. 

## <a name="next-steps"></a>Volgende stappen

- [Lopende of voltooide herstelacties weergeven na een geautomatiseerd onderzoek in Office 365](air-review-approve-pending-completed-actions.md)

- [Details en resultaten van een geautomatiseerd onderzoek in Office 365](air-view-investigation-results.md)