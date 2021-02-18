---
title: Ingebouwde virusbeveiliging in SharePoint Online, OneDrive en Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Lees hoe in SharePoint Online virussen worden gedetecteerd in bestanden die gebruikers uploaden en waardoor gebruikers de bestanden niet kunnen downloaden of synchroniseren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0eafb9e5e2f0c9d86791fe83931276e420afcd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286499"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>Ingebouwde virusbeveiliging in SharePoint Online, OneDrive en Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)

Microsoft 365 gebruikt een veelgebruikte engine voor virusdetectie voor het scannen van bestanden die gebruikers uploaden naar SharePoint Online, OneDrive en Microsoft Teams. Deze beveiliging is inbegrepen bij alle abonnementen met SharePoint Online, OneDrive en Microsoft Teams.

> [!IMPORTANT]
> De ingebouwde antivirusmogelijkheden zijn een manier om virussen tegen te gaan. Ze zijn niet bedoeld als bescherming tegen malware in uw omgeving. We raden alle klanten aan om de beveiliging tegen malware op verschillende lagen te onderzoeken en te implementeren en best practices toe te passen voor het beveiligen van de bedrijfsinfrastructuur. Zie de roadmap voor beveiliging voor meer informatie over strategieën [en best practices.](security-roadmap.md)

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Wat gebeurt er wanneer een geïnfecteerd bestand wordt geüpload naar SharePoint Online?

De Microsoft 365-virusdetectie-engine wordt asynchroon binnen SharePoint Online uitgevoerd. **Niet alle bestanden worden automatisch gescand bij het uploaden.** Heuristics bepalen de bestanden die moeten worden gescand. Wanneer een bestand een virus bevat, wordt er een vlag aan het bestand toegevoegd, zodat het niet opnieuw kan worden gedownload. In april 2018 hebben we de limiet van 25 MB voor gescande bestanden verwijderd.

Dit is wat er gebeurt:

1. Een gebruiker uploadt een bestand naar SharePoint Online.
2. SharePoint Online bepaalt of het bestand voldoet aan de criteria voor een scan.
3. De virusdetectie-engine scant het bestand.
4. Als er een virus wordt gevonden, stelt de virusen engine een eigenschap in voor het bestand om aan te geven dat het geïnfecteerd is.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Wat gebeurt er wanneer een gebruiker een geïnfecteerd bestand probeert te downloaden met behulp van de browser?

Als een bestand is geïnfecteerd, kunnen gebruikers het niet downloaden van SharePoint Online met behulp van een browser.

Dit is wat er gebeurt:

1. Een gebruiker opent een webbrowser en probeert een geïnfecteerd bestand van SharePoint Online te downloaden.
2. De gebruiker krijgt een waarschuwing dat er een virus is gedetecteerd. De gebruiker krijgt standaard de mogelijkheid om het bestand te downloaden en dit op te schonen met de antivirussoftware op zijn eigen apparaat.

> [!NOTE]
>
> Beheerders kunnen de parameter *DisallowInfectedFileDownload* gebruiken op de cmdlet [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) in SharePoint Online PowerShell om te voorkomen dat gebruikers geïnfecteerde bestanden downloaden, zelfs in het venster met de waarschuwing tegen virussen. Zie [SharePoint Online PowerShell](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)gebruiken om te voorkomen dat gebruikers schadelijke bestanden downloaden.
>
> Zodra u de parameter *DisallowInfectedFileDownload* inschakelen, wordt de toegang tot de gedetecteerde/geblokkeerde bestanden volledig geblokkeerd voor gebruikers en beheerders.

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Wat gebeurt er wanneer de OneDrive-synchronisatieclient een geïnfecteerd bestand probeert te synchroniseren?

OneDrive-synchronisatiecl clients downloaden geen bestanden die virussen bevatten. De synchronisatieclient geeft een melding weer dat het bestand niet kan worden gesynchroniseerd.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Uitgebreide mogelijkheden met Microsoft Defender voor Office 365

Microsoft 365-organisaties die Microsoft Defender voor [Office 365](office-365-atp.md) hebben opgenomen in hun abonnement of die zijn aangeschaft als een invoeglage, kunnen veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams inschakelen voor verbeterde rapportage en beveiliging. Zie Veilige bijlagen voor [SharePoint, OneDrive](atp-for-spo-odb-and-teams.md)en Microsoft Teams voor meer informatie.

## <a name="related-articles"></a>Verwante artikelen

[Bescherming tegen malware en ransomware in Microsoft 365](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

Voor meer informatie over antivirussoftware in SharePoint Online, OneDrive en Microsoft Teams, bekijk 'Protect [against threats'](protect-against-threats.md) en 'Turn [on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams'.](turn-on-atp-for-spo-odb-and-teams.md)
