---
title: Enable archive mailboxes in the Security & Compliance Center (Archiefpostvakken inschakelen in het Office 365-beveiligings- en compliancecentrum)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
ms.custom: seo-marvel-apr2020
description: Lees hoe u het compliancecentrum kunt gebruiken om archiefpostvakken in te stellen ter ondersteuning van de vereisten voor het bewaren en bewaren van berichten in uw organisatie, eDiscovery en bewaring.
ms.openlocfilehash: 72aa3f194197140cd86463598a17ab07fbbd647a
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341686"
---
# <a name="enable-archive-mailboxes-in-the-compliance-center"></a>Archiefpostvakken inschakelen in het compliancecentrum

Archiveren in Microsoft 365 (ook wel *In-place archivering* genoemd) biedt gebruikers extra opslagruimte voor postvakken. Nadat u archiefpostvakken hebt ingeslagen, kunnen gebruikers berichten in hun archiefpostvakken openen en opslaan met behulp van Microsoft Outlook en de webversie van Outlook (voorheen Outlook Web App). Gebruikers kunnen ook berichten verplaatsen of kopiëren tussen hun primaire postvak en hun archiefpostvak. Ze kunnen ook verwijderde items uit de map Herstelbare items in het archiefpostvak herstellen met behulp van het hulpmiddel Verwijderde items herstellen.

> [!NOTE]
> De functie voor automatische uitbreiding van archivering in Microsoft 365 biedt extra opslag in archiefpostvakken. Als automatisch uitbreidende archivering is ingeschakeld en het oorspronkelijke opslagquotum van het archiefpostvak van een gebruiker wordt bereikt, wordt automatisch extra opslagruimte toegevoegd in Microsoft 365. Dit betekent dat gebruikers geen opslagruimte meer hebben voor postvakken en u niets hoeft te beheren nadat u het archiefpostvak in eerste instantie hebt ingeschakeld en archivering met automatisch uitvijven voor uw organisatie hebt ingeschakeld. Zie [Overview of unlimited archiving](unlimited-archiving.md) (Overzicht van onbeperkt archiveren in Office 365) voor meer informatie.

## <a name="get-the-necessary-permissions"></a>Verkrijg de benodigde machtigingen

De rol van e-mailgeadresseerde moet aan u zijn toegewezen in Exchange Online om archiefpostvakken in- of uit te schakelen. Deze rol is standaard toegewezen aan de rollengroepen Ontvangersbeheer en Organisatiebeheer op de pagina **Machtigingen** in het Exchange-beheercentrum. Als u de pagina **Archief** in het Beveiligings- en compliancecentrum niet ziet, vraagt u de beheerder om u de benodigde machtigingen toe te wijzen.

## <a name="enable-an-archive-mailbox"></a>Schakel een archiefpostvak in

1. Ga naar <https://compliance.microsoft.com> en meld u aan.

2. Klik in het linkerdeelvenster van het Microsoft365-compliancecentrum op **Informatiebeheer** en vervolgens op het **Archief**-tabblad.

   Er wordt een pagina **Archief** weergegeven. De **Archiefpostvak** geeft aan of een archiefpostvak voor elke gebruiker is ingeschakeld of uitgeschakeld.

   > [!NOTE]
   > Op de pagina **Archief** kunnen maximaal 500 gebruikers worden weergegeven.

4. Selecteer in de lijst met postvakken de gebruiker voor wie u het archiefpostvak wilt inschakelen.

   ![Klik op Inschakelen in het detailvenster van de geselecteerde gebruiker om het archiefpostvak in te schakelen](../media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)

5. Klik in het detailvenster voor de geselecteerde gebruiker op **Inschakelen**.

   Er wordt een waarschuwing weergegeven waarin wordt weergegeven dat items in het postvak van de gebruiker die ouder zijn dan het archiveringsbeleid dat aan het postvak is toegewezen, worden verplaatst naar het nieuwe archiefpostvak als u het archiefpostvak inschakelen. Twee jaar na de datum waarop het item in het postvak is bezorgd of door de gebruiker is gemaakt, worden items naar het archiefpostvak verplaatst met het standaardarchiefbeleid dat deel uitmaakt van het bewaarbeleid dat is toegewezen aan Exchange Online-postvakken. Zie de sectie **Meer ifnormatie** in dit artikel voor meer informatie.

6. Klik **Ja** om archiefpostvak in teschakelen.

   Het kan even duren voordat het archiefpostvak is aangemaakt. Wanneer het postvak is gemaakt, wordt **Archiefpostvak: ingeschakeld** weergegeven in het detailvenster voor de geselecteerde gebruiker. Mogelijk moet u op **Vernieuwen** ![pictogram Vernieuwen](../media/O365-MDM-Policy-RefreshIcon.gif) klikken om de informatie in het detailvenster bij te werken.

> [!TIP]
> U kunt ook bulksgewijs archiefpostvakken inschakelen door meerdere gebruikers te selecteren met uitgeschakelde archiefpostvakken (gebruik de Shift- of CTRL-toets). Nadat u meerdere postvakken hebt geselecteerd, klikt u **Inschakelen** in het detailvenster.

## <a name="disable-an-archive-mailbox"></a>Een archiefpostvak uitschakelen

U kunt ook de pagina **Archiveren** in het  Beveiligings- en compliancecentrum gebruiken om het archiefpostvak van een gebruiker uit te schakelen. Nadat u een archiefpostvak hebt uitgeschakeld, kunt u dit binnen 30 dagen na het uitschakelen opnieuw verbinden met het primaire postvak van de gebruiker. In dit geval wordt de oorspronkelijke inhoud van het archiefpostvak hersteld. Na 30 dagen wordt de inhoud van het oorspronkelijke archiefpostvak definitief verwijderd en kan deze niet meer worden hersteld. Dus als u het archief meer dan 30 dagen na het uitschakelen weer inschakelen, wordt er een nieuw archiefpostvak gemaakt.

Twee jaar na de datum waarop een bericht in het postvak van gebruikers wordt bezorgd, worden items naar het archiefpostvak verplaatst door het standaardbeleid voor archiveren dat is toegewezen. Als u het archiefpostvak van een gebruiker uitschakelt wordt er geen actie ondernomen op postvakitems en blijven deze in het primaire postvak van de gebruiker staan.

Een archiefpostvak uitschakelen:

1. Ga naar <https://compliance.microsoft.com> en meld u aan.

2. Klik in het linkerdeelvenster van het Microsoft365-compliancecentrum op **Informatiebeheer** en vervolgens op het **Archief**-tabblad.

   Er wordt een pagina **Archief** weergegeven. De **Archiefpostvak** geeft aan of een archiefpostvak voor elke gebruiker is ingeschakeld of uitgeschakeld.

   > [!NOTE]
   > Op de pagina **Archief** kunnen maximaal 500 gebruikers worden weergegeven.

3. Selecteer in de lijst met postvakken de gebruiker voor wie u het archiefpostvak wilt uitschakelen.

4. Klik in het detailvenster op **Uitschakelen**.

   Er wordt een waarschuwingsbericht weergegeven met de tekst dat u 30 dagen de tijd hebt om het archiefpostvak opnieuw in te stellen. Na 30 dagen worden alle gegevens in het archief definitief verwijderd.

5. Klik **Ja** om archiefpostvak uit te schakelen.

   Het kan even duren voordat het archiefpostvak is uitgeschakeld. Wanneer het postvak is uitgeschakeld, wordt **Archiefpostvak: uitgeschakeld** weergegeven in het detailvenster voor de geselecteerde gebruiker. Mogelijk moet u op **Vernieuwen** ![pictogram Vernieuwen](../media/O365-MDM-Policy-RefreshIcon.gif) klikken om de informatie in het detailvenster bij te werken.

> [!TIP]
> U kunt ook bulksgewijs archiefpostvakken uitschakelen door meerdere gebruikers te selecteren met ingeschakelde archiefpostvakken (gebruik de Shift- of CTRL-toets). Nadat u meerdere postvakken hebt geselecteerd, klikt u **Uitschakelen** in het detailvenster.

## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>Exchange Online PowerShell gebruiken om archiefpostvakken in of uit te schakelen

U kunt ook Exchange Online PowerShell gebruiken om archiefpostvakken in te schakelen. De belangrijkste reden om PowerShell te gebruiken, is dat u het archiefpostvak snel kunt inschakelen voor alle gebruikers in uw organisatie.

De eerste stap is verbinding maken met Exchange Online PowerShell. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor instructies.

Nadat u verbinding hebt met Exchange Online, kunt u de opdrachten in de volgende secties uitvoeren om archiefpostvakken in of uit te schakelen.

### <a name="enable-archive-mailboxes"></a>Archiveren van postvakken inschakelen

Voer de volgende opdracht uit als u het archiefpostvak voor één gebruiker wilt inschakelen.

```powershell
Enable-Mailbox -Identity <username> -Archive
```

Voer de volgende opdracht uit om het archiefpostvak in teschakelen voor alle gebruikers in uw organisatie (waarvan het archiefpostvak momenteel niet is ingeschakeld).

```powershell
Get-Mailbox -Filter {ArchiveGuid -Eq "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Enable-Mailbox -Archive
```

### <a name="disable-archive-mailboxes"></a>Archiveren van postvakken uitschakelen

Voer de volgende opdracht uit om het archiefpostvak voor één gebruiker uit te schakelen.

```powershell
Disable-Mailbox -Identity <username> -Archive
```

Voer de volgende opdracht uit om het archiefpostvak uit te schakelen voor alle gebruikers in uw organisatie (waarvan het archiefpostvak momenteel is ingeschakeld).

```powershell
Get-Mailbox -Filter {ArchiveGuid -Ne "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Disable-Mailbox -Archive
```

## <a name="more-information"></a>Meer informatie

- Wanneer een archiefpostvak is ingeschakeld, kunnen gebruikers berichten opslaan in hun archiefpostvak. Gebruikers hebben toegang tot hun archiefpostvakken via Microsoft Outlook en de webversie van Outlook. Met een van deze clienttoepassingen kunnen gebruikers berichten in hun archiefpostvak bekijken en berichten verplaatsen of kopiëren tussen hun primaire postvak en hun archiefpostvak. Gebruikers kunnen ook verwijderde items uit de map Herstelbare items in het archiefpostvak herstellen met behulp van het hulpmiddel Verwijderde items herstellen.

  Zie [Outlook-licentievereisten voor Exchange-functies](https://support.microsoft.com/office/46b6b7c5-c3ca-43e5-8424-1e2807917c99) voor een lijst met Outlook-licenties die In-Place-archivering ondersteunen.

- Met archiefpostvakken kunnen u en uw gebruikers voldoen aan de vereisten voor bewaren, eDiscovery en bewaring van uw organisatie. U kunt bijvoorbeeld het Exchange-bewaarbeleid van uw organisatie gebruiken om inhoud van postvakken te verplaatsen naar het archiefpostvak van gebruikers. Wanneer u het hulpmiddel Inhoud zoeken in het beveiligings- en compliancecentrum gebruikt om in het postvak van een gebruiker te zoeken naar specifieke inhoud, wordt ook naar het archiefpostvak van de gebruiker gezocht. En wanneer u een bewaring van postvakgegevens uit juridische procedure aanhoudt of een bewaarbeleid op het postvak van een gebruiker toe past, blijven de items in het archiefpostvak ook behouden.

- Nadat archiefpostvakken zijn ingeschakeld, kan uw organisatie profiteren van het standaard bewaarbeleid van Exchange (ook wel berichtenrecordbeheer of MRM-beleid genoemd) dat automatisch aan elk postvak wordt toegewezen. Wanneer een archiefpostvak is ingeschakeld, doet het standaardbewaardebeleid van Exchange automatisch het volgende:

  - Items die twee jaar of ouder zijn, worden vanuit het primaire postvak van een gebruiker naar het archiefpostvak verplaatst.

  - Verplaatst items van 14 dagen of ouder uit de map Herstelbare items in het primaire postvak naar de map Herstelbare items in het archiefpostvak.

- Zie voor meer informatie over archiefpostvakken en exchange-bewaarbeleid:

  - [ Bewaarlabels en bewaarbeleid in Exchange Online](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

  - [Een bewaarbeleid maken in Exchange Online](/exchange/security-and-compliance/messaging-records-management/default-retention-policy)

  - [Een archief en een verwijderingsbeleid instellen voor postvakken in uw organisatie](set-up-an-archive-and-deletion-policy-for-mailboxes.md)