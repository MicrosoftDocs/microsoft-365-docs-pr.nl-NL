---
title: ATP voor SharePoint, OneDrive en Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Meer informatie over Office 365 Advanced Threat Protection voor bestanden in SharePoint Online, OneDrive voor bedrijven en Microsoft teams.
ms.openlocfilehash: 194b8e45e573ae4c4cd1f3428a1f80c48e1d80c8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326863"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>ATP voor SharePoint, OneDrive en Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

ATP voor SharePoint, OneDrive en Microsoft teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) biedt een extra beveiligingslaag voor bestanden die al zijn gecontroleerd op het moment dat ze worden geüpload via de [algemene virusdetectie-engine in Microsoft 365](virus-detection-in-spo.md). Met ATP voor SharePoint, OneDrive en Microsoft teams kunt u bestaande bestanden die zijn geïdentificeerd als schadelijk op team sites en documentbibliotheken detecteren en blokkeren.

ATP voor SharePoint, OneDrive en Microsoft teams is standaard niet ingeschakeld. Als u dit wilt inschakelen, raadpleegt u [ATP voor SharePoint, OneDrive en Microsoft teams inschakelen](turn-on-atp-for-spo-odb-and-teams.md).

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a>De werking van ATP voor SharePoint, OneDrive en Microsoft teams

Wanneer ATP voor SharePoint, OneDrive en Microsoft teams is ingeschakeld en een bestand als schadelijk wordt geïdentificeerd, wordt het bestand vergrendeld via rechtstreekse integratie met de bestandsarchieven. In de volgende afbeelding ziet u een voorbeeld van een schadelijk bestand dat is gevonden in een bibliotheek.

![Bestanden in OneDrive voor bedrijven met een gedetecteerde schadelijke versie](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

Hoewel het geblokkeerde bestand nog steeds wordt weergegeven in de documentbibliotheek en in Internet-, mobiele en bureaubladtoepassingen, kunnen personen het bestand niet openen, kopiëren, verplaatsen of delen. Maar ze kunnen het geblokkeerde bestand wel verwijderen.

Hier ziet u een voorbeeld van hoe een geblokkeerd bestand eruit ziet op een mobiel apparaat:

![Een geblokkeerd bestand verwijderen uit OneDrive voor bedrijven uit de mobiele OneDrive-app](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

Standaard kunnen personen een geblokkeerd bestand downloaden. Het downloaden van een geblokkeerd bestand ziet er als volgt uit op een mobiel apparaat:

![Een geblokkeerd bestand downloaden in OneDrive voor bedrijven](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online-beheerders kunnen voorkomen dat mensen schadelijke bestanden downloaden. Zie [SharePoint Online PowerShell gebruiken om te voorkomen dat gebruikers schadelijke bestanden downloaden](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)voor instructies.

Zie [wat u moet doen als er een schadelijk bestand wordt gevonden in SharePoint Online, OneDrive of Microsoft teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)voor meer informatie over de gebruikerservaring wanneer een bestand als schadelijk is gedetecteerd.

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Informatie weergeven over schadelijke bestanden die zijn gedetecteerd door ATP voor SharePoint, OneDrive en Microsoft teams

Bestanden die worden geïdentificeerd als schadelijk voor ATP, worden weergegeven in [rapporten voor Office 365 Advanced Threat Protection](view-reports-for-atp.md) en in [Explorer (en realtime-detectie)](threat-explorer.md).

Vanaf mei 2018 wordt het bestand ook in quarantaine geplaatst wanneer een bestand wordt geïdentificeerd als schadelijk voor ATP. Zie voor meer informatie het artikel over [beveiligings & voor nalevings centrum voor het beheren van gequarantinee bestanden](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).

## <a name="keep-these-points-in-mind"></a>Let op de volgende punten

- Met ATP kunt u niet elk afzonderlijk bestand in SharePoint Online, OneDrive voor bedrijven of Microsoft teams scannen. Dit is inherent aan het ontwerp van het product. Bestanden worden asynchroon gescand. Met de functie voor het delen van gebeurtenissen en gebeurtenissen in een gast activiteit worden kwaadwillende bestanden aangegeven met behulp van slimme heuristisch en bedreigings signalen.

- Zorg ervoor dat de SharePoint-sites zijn geconfigureerd voor gebruik van de [moderne ervaring](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). ATP-beveiliging is van toepassing op de meest recente ervaring of de klassieke weergave. de visuele indicatoren die een bestand blokkeert, zijn echter alleen beschikbaar in de moderne ervaring.

- ATP voor SharePoint, OneDrive en Microsoft teams maakt deel uit van de algemene strategie voor risico beveiliging van uw organisatie, waaronder antispam en bescherming tegen malware in Exchange Online Protection (EOP), en veilige koppelingen en veilige bijlagen in Office 365 ATP. Voor meer informatie raadpleegt u [bescherming tegen bedreigingen in Office 365](protect-against-threats.md).
