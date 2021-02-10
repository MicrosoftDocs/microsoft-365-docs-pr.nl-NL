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
description: Meer informatie over Microsoft Defender voor Office 365 voor bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 640867cb38dab650bca990fe36c0b7cea7f6a0d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175725"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams in Microsoft Defender voor [Office 365](office-365-atp.md) bieden een extra beveiligingslaag voor bestanden die al tijdens het uploaden zijn gescand met de algemene [virusdetectie-engine in Microsoft 365.](virus-detection-in-spo.md) Met veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams kunt u bestaande bestanden opsporen en blokkeren die in teamsites en documentbibliotheken als schadelijk zijn aangemerkt.

Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams zijn standaard niet ingeschakeld. Zie Veilige bijlagen in schakel je in voor [SharePoint, OneDrive en Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>Hoe veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams werken

Als veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams zijn ingeschakeld en een bestand als schadelijk wordt geïdentificeerd, wordt het bestand vergrendeld met rechtstreekse integratie met de bestandsopslag. In de volgende afbeelding ziet u een voorbeeld van een schadelijk bestand dat in een bibliotheek is gedetecteerd.

![Bestanden in OneDrive voor Bedrijven met een gedetecteerd als schadelijk](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Hoewel het geblokkeerde bestand nog steeds wordt vermeld in de documentbibliotheek en in web-, mobiele of bureaubladtoepassingen, kunnen personen het bestand niet openen, kopiëren, verplaatsen of delen. Maar ze kunnen het geblokkeerde bestand verwijderen.

Hier ziet u een voorbeeld van hoe een geblokkeerd bestand eruitziet op een mobiel apparaat:

![Een geblokkeerd bestand verwijderen uit OneDrive voor Bedrijven vanuit de mobiele OneDrive-app](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Standaard kunnen mensen een geblokkeerd bestand downloaden. Zo ziet het downloaden van een geblokkeerd bestand er op een mobiel apparaat uit:

![Een geblokkeerd bestand downloaden in OneDrive voor Bedrijven](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online-beheerders kunnen voorkomen dat personen schadelijke bestanden downloaden. Zie [SharePoint Online PowerShell gebruiken om te](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)voorkomen dat gebruikers schadelijke bestanden downloaden.

Als u meer wilt weten over de gebruikerservaring wanneer een bestand als schadelijk is gedetecteerd, bekijkt u Wat u moet doen als er een schadelijk bestand wordt gevonden [in SharePoint Online, OneDrive of Microsoft Teams.](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Informatie weergeven over schadelijke bestanden die worden gedetecteerd door veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams

Bestanden die worden geïdentificeerd als schadelijk door Microsoft Defender voor Office 365, worden weergegeven in rapporten voor Microsoft Defender voor [Office 365](view-reports-for-atp.md) en in [Verkenner (en realtime detecties).](threat-explorer.md)

Vanaf mei 2018, wanneer een bestand wordt geïdentificeerd als schadelijk door Microsoft Defender voor Office 365, is het bestand ook in quarantaine beschikbaar. Zie het beveiligingscentrum voor & voor meer informatie [over het beheren van bestanden in quarantaine.](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)

## <a name="keep-these-points-in-mind"></a>Houd rekening met deze punten

- Defender voor Office 365 scant niet elk bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams. Dit is inherent aan het ontwerp van het product. Bestanden worden asynchroon gescand. Het proces maakt gebruik van gebeurtenissen voor delen en gastactiviteiten, samen met slimme heuristics- en bedreigingssignalen om schadelijke bestanden te identificeren.

- Zorg ervoor dat uw SharePoint-sites zijn geconfigureerd voor gebruik met de [moderne ervaring.](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience) De beveiliging van Defender voor Office 365 is van toepassing, ongeacht of de moderne of klassieke weergave wordt gebruikt. Visuele indicatoren die echter zeggen dat een bestand is geblokkeerd, zijn alleen beschikbaar in de moderne ervaring.

- Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams maken deel uit van de algemene strategie voor risicobeveiliging van uw organisatie, waaronder bescherming tegen ongewenste e-mail en malware in Exchange Online Protection (EOP), evenals veilige koppelingen en veilige bijlagen in Microsoft Defender voor Office 365. Zie Beveiligen tegen bedreigingen [in Office 365 voor meer informatie.](protect-against-threats.md)
