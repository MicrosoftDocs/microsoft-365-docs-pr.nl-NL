---
title: Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Meer informatie over Microsoft Defender Office 365 voor bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc4157d9f3d2114375d4136fec694250e8fbeb64
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821353"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams in [Microsoft Defender](whats-new-in-defender-for-office-365.md) voor Office 365 bieden een extra beveiligingslaag voor bestanden die al zijn gescand tijdens het uploaden door de algemene [virusdetectie-engine in Microsoft 365.](virus-detection-in-spo.md) Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams helpt bij het opsporen en blokkeren van bestaande bestanden die zijn geïdentificeerd als schadelijk in teamsites en documentbibliotheken.

Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams is standaard niet ingeschakeld. Zie Safe Bijlagen in SharePoint, OneDrive en [Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Hoe Safe bijlagen voor SharePoint, OneDrive en Microsoft Teams werken

Wanneer Safe bijlagen voor SharePoint, OneDrive en Microsoft Teams is ingeschakeld en een bestand als schadelijk wordt geïdentificeerd, wordt het bestand vergrendeld met behulp van directe integratie met de bestandsopslag. In de volgende afbeelding ziet u een voorbeeld van een schadelijk bestand dat is gedetecteerd in een bibliotheek.

![Bestanden in OneDrive voor Bedrijven met een gedetecteerd als schadelijk](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Hoewel het geblokkeerde bestand nog steeds wordt weergegeven in de documentbibliotheek en in web-, mobiele of desktoptoepassingen, kunnen personen het bestand niet openen, kopiëren, verplaatsen of delen. Maar ze kunnen het geblokkeerde bestand verwijderen.

Hier ziet u een voorbeeld van hoe een geblokkeerd bestand eruitziet op een mobiel apparaat:

![Een geblokkeerd bestand verwijderen uit OneDrive voor Bedrijven mobiele OneDrive app](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Standaard kunnen personen een geblokkeerd bestand downloaden. Zo ziet het downloaden van een geblokkeerd bestand eruit op een mobiel apparaat:

![Een geblokkeerd bestand downloaden in OneDrive voor Bedrijven](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Onlinebeheerders kunnen voorkomen dat personen schadelijke bestanden downloaden. Zie Gebruik SharePoint [Online PowerShell](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)om te voorkomen dat gebruikers schadelijke bestanden downloaden voor instructies.

Zie Wat u moet doen wanneer een schadelijk bestand wordt gevonden [in SharePoint Online, OneDrive](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)of Microsoft Teams voor meer informatie over de gebruikerservaring wanneer een bestand is gedetecteerd als schadelijk.

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Informatie weergeven over schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams

Bestanden die zijn geïdentificeerd als schadelijk door Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams worden weergegeven in rapporten voor [Microsoft Defender](view-reports-for-mdo.md) voor Office 365 en in [Explorer (en realtime detecties)](threat-explorer.md).

Vanaf mei 2018, wanneer een bestand wordt geïdentificeerd als schadelijk door Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams, is het bestand ook beschikbaar in quarantaine. Zie Het beveiligingscentrum gebruiken voor het beheren van in quarantaine geplaatste bestanden in Defender voor [Office 365.](manage-quarantined-messages-and-files.md#use-the-security-center-to-manage-quarantined-files-in-defender-for-office-365)

## <a name="keep-these-points-in-mind"></a>Houd rekening met deze punten

- Defender voor Office 365 scant niet elk bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams. Dit is inherent aan het ontwerp van het product. Bestanden worden asynchroon gescand. In het proces worden gebeurtenissen voor delen en gastactiviteit gebruikt, samen met slimme heuristische en bedreigingssignalen om schadelijke bestanden te identificeren.

- Zorg ervoor dat SharePoint sites zijn geconfigureerd voor gebruik van [de moderne ervaring.](/sharepoint/guide-to-sharepoint-modern-experience) Defender for Office 365 protection is van toepassing of de moderne ervaring of de klassieke weergave wordt gebruikt. Visuele indicatoren dat een bestand is geblokkeerd, zijn echter alleen beschikbaar in de moderne ervaring.

- Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams maken deel uit van de algemene strategie voor bedreigingsbeveiliging van uw organisatie, waaronder antispam- en anti-malwarebeveiliging in Exchange Online Protection (EOP), evenals Safe Koppelingen en Safe Bijlagen in Microsoft Defender voor Office 365. Zie Beschermen tegen bedreigingen [in](protect-against-threats.md)Office 365.
