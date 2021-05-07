---
title: Onbeperkt archiveren inschakelen - Help voor beheerders
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 'Voor beheerders: Informatie over het inschakelen van automatisch uitbreidende archivering, waardoor uw gebruikers onbeperkte opslagruimte hebben voor hun Exchange Online postvakken. U kunt automatisch uitbreidende archivering inschakelen voor uw hele organisatie of alleen voor specifieke gebruikers.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ac5661ac43ed9c0f35eba20007f0c4c4406ebf20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162174"
---
# <a name="enable-unlimited-archiving---admin-help"></a>Onbeperkt archiveren inschakelen - Help voor beheerders

U kunt de functie Exchange Online archiveren automatisch uitbreiden gebruiken om onbeperkte opslagruimte in te stellen voor archiefpostvakken. Wanneer automatisch archiveren is ingeschakeld, wordt automatisch extra opslagruimte toegevoegd aan het archiefpostvak van een gebruiker wanneer de opslaglimiet wordt bereikt. Het resultaat is een onbeperkte postvakopslagcapaciteit. U kunt archivering automatisch uitbreiden in te zetten voor iedereen in uw organisatie of alleen voor specifieke gebruikers. Zie Overzicht van onbeperkt archiveren in Office 365 voor meer informatie over het automatisch uitbreiden [van archivering.](unlimited-archiving.md)

## <a name="before-you-enable-auto-expanding-archiving"></a>Voordat u automatisch archiveren inschakelen

- U moet een globale beheerder in uw organisatie of lid zijn van de rollengroep Organisatiebeheer in uw Exchange Online-organisatie om automatisch uit te breiden archivering in te stellen voor uw hele organisatie of voor specifieke gebruikers. U moet ook lid zijn van een rollengroep die de rol E-mailontvangers heeft toegewezen om het automatisch uitbreiden van archivering voor specifieke gebruikers mogelijk te maken.

- Het archiefpostvak van een gebruiker moet zijn ingeschakeld voordat u het automatisch uitbreiden van archivering kunt inschakelen. Aan een gebruiker moet een licentie Exchange Online abonnement 2 worden toegewezen om het archiefpostvak in te stellen. Als aan een gebruiker een licentie Exchange Online abonnement 1 is toegewezen, moet u deze een afzonderlijke Exchange Online Archiving toewijzen om het archiefpostvak in te stellen. Zie [Archiefpostvakken inschakelen in het Beveiligings- & Compliancecentrum](enable-archive-mailboxes.md).

- U kunt PowerShell ook gebruiken om archiefpostvakken in te stellen. Zie de [sectie Meer informatie](#more-information) voor een voorbeeld van de PowerShell-opdracht die u kunt gebruiken om archiefpostvakken in te stellen voor alle gebruikers in uw organisatie.

- Het automatisch uitbreiden van archivering ondersteunt ook gedeelde postvakken. Als u het archief voor een gedeeld postvak wilt inschakelen, is een Exchange Online Abonnement 2-licentie of een Exchange Online Abonnement 1-licentie met een Exchange Online Archiving licentie vereist.

- Door archivering automatisch uit te breiden, voorkomt u dat u een [inactief postvak herstelt of herstelt.](inactive-mailboxes-in-office-365.md#what-are-inactive-mailboxes) Dit betekent dat als u automatisch uit te breiden archivering inschakelen voor een postvak en het postvak op een later tijdstip inactief wordt gemaakt, u het [inactieve](recover-an-inactive-mailbox.md) postvak niet kunt herstellen (door het te converteren naar een actief postvak) of te herstellen [(door](restore-an-inactive-mailbox.md) de inhoud samen te voegen in een bestaand postvak). Als automatisch uitbreiden van archivering is ingeschakeld in een inactief postvak, kunt u alleen gegevens herstellen met behulp van het zoekprogramma Inhoud in het Microsoft 365-compliancecentrum om de gegevens uit het postvak te exporteren en te importeren naar een ander postvak. Zie de sectie 'Inactieve postvakken en automatisch uitbreidende archieven' in [Overzicht van inactieve postvakken](inactive-mailboxes-in-office-365.md#inactive-mailboxes-and-auto-expanding-archives)voor meer informatie.

- U kunt het beheercentrum Exchange beveiligingscentrum & compliancecentrum niet gebruiken om automatisch uit te breiden archiveren. U moet powershell Exchange Online gebruiken. Als u verbinding wilt maken met uw Exchange Online met behulp van externe PowerShell, Verbinding maken [powershell Exchange Online maken.](/powershell/exchange/connect-to-exchange-online-powershell)

## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Automatisch uitbreiden van archivering inschakelen voor uw hele organisatie

U kunt automatisch uitbreidende archivering inschakelen voor uw hele organisatie. Nadat u deze hebt ingeschakeld, wordt automatisch archiveren ingeschakeld voor bestaande gebruikerspostvakken en voor nieuwe gebruikerspostvakken die worden gemaakt. Wanneer u gebruikerspostvakken maakt, moet u het hoofdarchiefpostvak van de gebruiker inschakelen, zodat de functie voor automatisch uitvijven voor het nieuwe gebruikerspostvak werkt.
  
1. [Verbinding maken powershell Exchange Online gebruiken](/powershell/exchange/connect-to-exchange-online-powershell)

2. Voer de volgende opdracht uit in Exchange Online PowerShell om automatisch uit te breiden archivering voor uw hele organisatie in te stellen.

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Archivering automatisch uitbreiden voor specifieke gebruikers inschakelen

In plaats van het automatisch uitbreiden van archivering in te stellen voor elke gebruiker in uw organisatie, kunt u het alleen inschakelen voor specifieke gebruikers. U kunt dit doen omdat alleen sommige gebruikers behoefte hebben aan een grote archiefopslagcapaciteit.
  
Wanneer u automatisch uitbreidende archivering inschakelen voor een specifieke gebruiker en het postvak van de gebruiker in bewaring of toegewezen aan een bewaarbeleid, worden de volgende twee configuraties gewijzigd:
  
- Het opslagquotum voor het primaire archiefpostvak van de gebruiker wordt verhoogd met 10 GB (van 100 GB naar 110 GB). Het waarschuwingsquotum voor het archief wordt ook verhoogd met 10 GB (van 90 GB naar 100 GB).

- Het opslagquotum voor de map Herstelbare items in het primaire postvak van de gebruiker wordt verhoogd met 10 GB (ook van 100 GB naar 110 GB). Het waarschuwingsquotum Herstelbare items wordt ook verhoogd met 10 GB (van 90 GB naar 100 GB). Deze wijzigingen zijn alleen van toepassing als het postvak in bewaring staat of is toegewezen aan een bewaarbeleid.

Deze extra ruimte wordt toegevoegd om te voorkomen dat er opslagproblemen optreden voordat het automatisch uitbreidende archief is ingericht. Extra opslagruimte  *wordt niet toegevoegd*  wanneer u automatisch uitbreidende archivering inschakelen voor uw hele organisatie, zoals wordt beschreven in de vorige sectie.
  
1. [Verbinding maken powershell Exchange Online gebruiken](/powershell/exchange/connect-to-exchange-online-powershell)

2. Voer de volgende opdracht uit in Exchange Online PowerShell om automatisch uit te breiden archiveren voor een specifieke gebruiker. Zoals eerder is uitgelegd, moet het archiefpostvak (hoofdarchief) van de gebruiker zijn ingeschakeld voordat u het automatisch uitbreiden van archivering voor die gebruiker kunt inschakelen.

    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```

> [!IMPORTANT]
> In een Exchange hybride implementatie kunt u de opdracht **Enable-Mailbox -AutoExpandingArchiveren** niet gebruiken om automatisch uitbreidende archivering in te stellen voor een specifieke gebruiker van wie het primaire postvak on-premises is en waarvan het archiefpostvak cloudgebaseerd is. Als u automatisch uitbreidende archivering wilt inschakelen voor archiefpostvakken in de cloud in een hybride implementatie van Exchange, moet u de opdracht **Set-OrganizationConfig -AutoExpandingArchiveren** uitvoeren in Exchange Online PowerShell om automatisch uitbreidende archivering voor de hele organisatie mogelijk te maken. Als de primaire postvakken en archiefpostvakken van een gebruiker zowel cloudgebaseerd zijn, kunt u de opdracht Postvak inschakelen **-AutoExpandingArchiveren** gebruiken om het automatisch uitbreiden van archivering voor die specifieke gebruiker in te stellen.
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Controleren of archivering automatisch uit te breiden is ingeschakeld

Als u wilt controleren of het automatisch uitbreiden van archivering is ingeschakeld voor uw organisatie, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell.

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Een waarde van  `True` geeft aan dat automatisch uitbreidende archivering is ingeschakeld voor de organisatie. 
  
Als u wilt controleren of het automatisch uitbreiden van archivering is ingeschakeld voor een specifieke gebruiker, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell.
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

Een waarde van  `True` geeft aan dat automatisch uitbreidende archivering is ingeschakeld voor de gebruiker.
  
Als u wilt bepalen of het automatisch uitbreiden van archivering is ingeschakeld voor inactieve postvakken, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL UserPrincipalName,AutoExpandingArchiveEnabled
```

Een waarde van  `True` geeft aan dat automatisch uitbreidende archivering is ingeschakeld voor het inactieve postvak. Een waarde van geeft aan dat het automatisch uitbreiden van `False` archivering niet is ingeschakeld.

Houd rekening met de volgende dingen nadat u het automatisch uitbreiden van archivering hebt ingeschakeld:
  
- Als u de opdracht **Set-OrganizationConfig -AutoExpandingArchiveren** uitzet om automatisch uitbreidende archivering voor uw organisatie in te stellen, hoeft u de opdracht **Enable-Mailbox -AutoExpandingArchiveren** niet uit te voeren op afzonderlijke postvakken. Als u de cmdlet **Set-OrganizationConfig** voor het automatisch uitbreiden van archivering voor uw organisatie inschakelen, wordt de eigenschap  *AutoExpandingArchiveEnabled*  in gebruikerspostvakken niet gewijzigd in `True` .

- Op dezelfde manier worden de waarden voor de eigenschappen  *ArchiveQuota*  en  *ArchiveWarningQuota niet*  gewijzigd wanneer u automatisch archiveren inschakelen. Wanneer u automatisch uitbreidende archivering inschakelen voor een gebruikerspostvak en de eigenschap  *AutoExpandingArchiveEnabled*  is ingesteld op , worden de eigenschappen  `True`  *ArchiveQuota*  en  *ArchiveWarningQuota*  genegeerd. Hier volgen een voorbeeld van deze postvakeigenschappen nadat automatisch archiveren is ingeschakeld voor het postvak van een gebruiker. 

    ![Eigenschappen ArchiveQuota en ArchiveWarningQuota worden genegeerd nadat u automatisch uitbreidende archivering hebt ingeschakeld](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

## <a name="more-information"></a>Meer informatie

- U kunt PowerShell ook gebruiken om archiefpostvakken in te stellen. U kunt bijvoorbeeld de volgende opdracht uitvoeren in Exchange Online PowerShell om archiefpostvakken in te stellen voor alle gebruikers van wie het archiefpostvak nog niet is ingeschakeld.

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- Nadat u archivering automatisch uitbreidt voor uw organisatie of voor een specifieke gebruiker, wordt een archiefpostvak geconverteerd naar een automatisch uitvijvend archief wanneer het archiefpostvak (inclusief de map Herstelbare items) 90 GB bereikt. Het kan tot 30 dagen duren voordat de extra opslagruimte is ingericht.

- Nadat u archivering automatisch uit te breiden hebt ingeschakeld, kan het niet worden uitgeschakeld. Bovendien kunnen beheerders het opslagquotum voor het automatisch uitbreiden van archivering niet aanpassen.

- Automatisch uitbreiden van archivering wordt ondersteund voor archiefpostvakken in de cloud in een Exchange hybride implementatie voor gebruikers die een on-premises primair postvak hebben. Nadat automatisch uitbreiden van archivering is ingeschakeld voor een archiefpostvak in de cloud, kunt u dat archiefpostvak echter niet terug naar de on-premises Exchange organisatie. Automatisch archiveren wordt niet ondersteund voor on-premises postvakken in een versie van Exchange Server.

- Zie de sectie 'Outlook requirements for accessing items in an auto-expanded archive' in [Overview of unlimited archiving](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)(Overzicht van onbeperkt archiveren) voor een lijst met Outlook-clients die gebruikers kunnen gebruiken om toegang te krijgen tot items in het extra opslaggebied in hun archiefpostvak.

- Zoals eerder uitgelegd, wordt 10 GB toegevoegd aan het opslagquotum van het primaire archiefpostvak van de gebruiker (en aan de map Herstelbare items als het postvak in de wacht staat) wanneer u de opdracht **Inschakelen-Postvak -AutoExpandingArchiveren** uitwerkt. Dit biedt extra opslagruimte totdat de automatisch uitveerde opslagruimte is ingericht (wat tot 30 dagen kan duren). Deze extra opslagruimte wordt niet toegevoegd wanneer u **Set-OrganizationConfig -AutoExpandingArchiveren** gebruikt om automatisch uitvijven van archivering in te stellen voor alle postvakken in uw organisatie. Als u het automatisch uitbreiden van archivering voor de hele organisatie hebt ingeschakeld, maar de extra 10 GB opslagruimte voor een specifieke gebruiker moet toevoegen, kunt u de opdracht **Enable-Mailbox -AutoExpandingArchiveren** uitvoeren op dat postvak. Er wordt een foutmelding weergegeven dat het automatisch uitbreiden van archivering al is ingeschakeld, maar dat de extra opslagruimte aan het postvak wordt toegevoegd.

> [!IMPORTANT]
> Het automatisch uitbreiden van archivering wordt alleen ondersteund voor postvakken die worden gebruikt voor individuele gebruikers of gedeelde postvakken met een groeipercentage dat niet groter is dan 1 GB per dag. Het is niet toegestaan logboekregels, transportregels of regels voor automatisch doorsturen te gebruiken om berichten te kopiëren naar een archiefpostvak voor archivering. Het archiefpostvak van een gebruiker is alleen bedoeld voor die gebruiker. Microsoft behoudt zich het recht voor om onbeperkt archiveren te weigeren in gevallen waarin het archiefpostvak van een gebruiker wordt gebruikt voor het opslaan van archiefgegevens voor andere gebruikers of in andere gevallen van ongepast gebruik.