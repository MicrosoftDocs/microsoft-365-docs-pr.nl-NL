---
title: Herstelacties in automatisch onderzoek en reactie van Office 365
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, respons, sanering, bedreigingen, geavanceerd, bedreiging, bescherming
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
description: Meer informatie over herstelacties in geautomatiseerde onderzoeks- en reactiemogelijkheden in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955531"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Herstelacties na een geautomatiseerd onderzoek in Office 365

## <a name="remediation-actions"></a>Herstelacties

[Geautomatiseerde onderzoeks- en reactiemogelijkheden](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 omvatten bepaalde herstelacties. Wanneer een geautomatiseerd onderzoek wordt uitgevoerd of is voltooid, ziet u doorgaans een of meer herstelacties waarvoor goedkeuring door uw beveiligingsteam nodig is om door te gaan. 

In de volgende tabel worden de herstelacties samengevat die momenteel beschikbaar zijn in Office 365 ATP. 

|Actie | Beschrijving |
|-----|-----|
|URL blokkeren (kliktijd) |Beschermt tegen e-mailberichten en documenten die schadelijke URL's bevatten. Dit maakt het blokkeren van kwaadaardige links en gerelateerde webpagina's via [Veilige Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) mogelijk wanneer de gebruiker op een koppeling in een bestaand Office-bestand of in een ouder e-mailbericht klikt. |
|E-mail met zachte verwijdering  |Soft verwijdert specifieke e-mailberichten uit het postvak van een gebruiker. <br/>Een bericht met zachte berichten wordt verplaatst naar de map Herstelbare items van een gebruiker en wordt bewaard totdat de bewaartermijn voor verwijderde items is verstreken. |
|E-mailclusters voor het verwijderen van zachte verwijderen  |Soft verwijdert schadelijke e-mailberichten die overeenkomen met een query uit de postvakken van alle gebruikers. <br/>Verwijderde berichten worden verplaatst naar de map Herstelbare items van gebruikers en worden bewaard totdat de bewaartermijn voor verwijderde items is verstreken. |
|Extern doorsturen van e-mail uitschakelen |Hiermee verwijdert u een doorstuurregel uit het postvak van een specifieke eindgebruiker.|

> [!NOTE]
> In Office 365 ATP worden automatisch geen herstelacties uitgevoerd. Herstelacties worden alleen uitgevoerd na goedkeuring door het beveiligingsteam van uw organisatie. 

## <a name="next-steps"></a>Volgende stappen

- [Inbehandeling of voltooide herstelacties weergeven na een geautomatiseerd onderzoek in Office 365](air-review-approve-pending-completed-actions.md)

- [Details en resultaten van een geautomatiseerd onderzoek in Office 365](air-view-investigation-results.md)

## <a name="related-articles"></a>Verwante artikelen

- [Geautomatiseerd onderzoek in Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft-bedreigingsbeveiliging](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)