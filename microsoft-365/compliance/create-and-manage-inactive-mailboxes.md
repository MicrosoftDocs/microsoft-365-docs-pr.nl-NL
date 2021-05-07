---
title: Inactieve postvakken maken en beheren
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
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
ms.custom:
- seo-marvel-apr2020
description: Behoudt de inhoud van verwijderde postvakken met behulp van de functie inactieve postvakken in Microsoft 365.
ms.openlocfilehash: acd00fedcf0949b7d0c9f85c17039105e9b34821
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162860"
---
# <a name="create-and-manage-inactive-mailboxes"></a>Inactieve postvakken maken en beheren

Microsoft 365 kunt u de inhoud van verwijderde postvakken behouden. Deze functie wordt [inactieve postvakken genoemd.](inactive-mailboxes-in-office-365.md) Met inactieve postvakken kunt u de e-mail van voormalige werknemers behouden nadat ze uw organisatie hebben verlaten. Een postvak wordt inactief wanneer een bewaringsbeleid (gemaakt in het beveiligings- en compliancecentrum in Office 365 of Microsoft 365) wordt toegepast op het postvak voordat het bijbehorende gebruikersaccount wordt verwijderd. De inhoud van een inactief postvak blijft behouden gedurende de duur van de wacht die in het postvak is geplaatst voordat het inactief werd gemaakt. Hierdoor kunnen beheerders, compliancemedewerkers en recordmanagers Inhoud zoeken gebruiken om de inhoud van een inactief postvak te doorzoeken en te exporteren. Inactieve postvakken kunnen geen e-mail ontvangen en worden niet weergegeven in het gedeelde adresboek van uw organisatie of in andere lijsten.
  
> [!IMPORTANT]
> Terwijl we op verschillende manieren blijven investeren om postvakinhoud te behouden, kondigen we de uittreding aan van In-Place Holds in het Exchange beheercentrum. Dit betekent dat u beleidsregels voor bewaring en bewaring van rechtszaken moet gebruiken om een inactief postvak te maken. Vanaf 1 juli 2020 kunt u geen nieuwe In-Place in Exchange Online. Maar u kunt de duur van de wachttijd van een In-Place in een inactief postvak wijzigen. Vanaf 1 oktober 2020 kunt u de duur van de wachttijd echter niet wijzigen. U kunt alleen een inactief postvak verwijderen door de In-Place verwijderen. Bestaande inactieve postvakken die in de wacht In-Place blijven behouden totdat de wacht wordt verwijderd. Zie Retirement of legacy eDiscovery tools (Oude eDiscovery-hulpprogramma's) voor meer informatie over het In-Place van [eDiscovery-functies.](legacy-ediscovery-retirement.md)
  
## <a name="preparations-before-creating-an-inactive-mailbox"></a>Voorbereidingen voor het maken van een inactief postvak

- Als u een postvak inactief wilt maken, moet er een licentie Exchange Online Plan 2 aan het postvak worden toegewezen, zodat een bewaringstermijn of bewaarbeleid kan worden toegepast op het postvak voordat het wordt verwijderd. Exchange Online Abonnement 2-licenties maken deel uit van een Office 365 Enterprise E3- en E5-abonnement. Als aan een postvak een Exchange Online Abonnement 1- of Exchange Online Kiosk-licentie is toegewezen (die respectievelijk deel uitmaken van een Office 365 E1- en F1-abonnement), moet u het een aparte Exchange Online Archiving-licentie toewijzen, zodat er een hold kan worden toegepast op het postvak voordat het wordt verwijderd. Zie voor meer informatie [Exchange Online Archiving.](https://go.microsoft.com/fwlink/p/?LinkId=286153)

- De licenties die zijn gekoppeld aan het verwijderde Exchange Online postvak zijn beschikbaar nadat u het bijbehorende gebruikersaccount hebt verwijderd. U kunt deze [licenties vervolgens toewijzen aan een andere gebruiker.](../admin/manage/assign-licenses-to-users.md)

- Als een bewaring van rechtszaken of een bewaarbeleid (dat is geconfigureerd om inhoud te behouden of te behouden en vervolgens te verwijderen) niet wordt toegepast op een postvak voordat het wordt verwijderd, wordt de inhoud van het postvak niet bewaard of detecteerbaar. Het verwijderde postvak kan echter binnen 30 dagen na verwijdering worden hersteld, maar het postvak en de inhoud ervan worden na 30 dagen definitief verwijderd als het niet wordt hersteld.

- Zie Litigation Hold voor meer informatie over Het in de wacht houden [van rechtszaken.](/exchange/security-and-compliance/in-place-and-litigation-holds) Zie Bewaarbeleid en bewaarlabels voor meer informatie over [bewaarbeleid.](retention.md)
  
## <a name="create-an-inactive-mailbox"></a>Een inactief postvak maken

Het inactief maken van een postvak bestaat uit twee stappen: 1) het postvak in bewaring plaatsen of een bewaarbeleid toepassen op het postvak en 2) het postvak of bijbehorende gebruikersaccount verwijderen. Nadat het postvak inactief is, blijft de inhoud behouden totdat het bewaar- of bewaringsbeleid is verwijderd.
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-a-retention-policy"></a>Stap 1: Een postvak in bewaring plaatsen of een bewaarbeleid toepassen

Als u een postvak in bewaring plaatst of een bewaarbeleid (dat is geconfigureerd voor het behouden of behouden en vervolgens verwijderen van inhoud) in bewaring plaatst, blijft de inhoud in het postvak behouden voordat deze wordt verwijderd. Alle postvakinhoud, inclusief verwijderde items en oorspronkelijke versies van gewijzigde items, blijft behouden voor beide typen ingehouden postvakken. Verwijderde en gewijzigde items worden bewaard in het inactieve postvak voor een bepaalde periode of totdat u het inactieve postvak definitief verwijdert door het bewaringsbeleid te verwijderen dat is toegepast op het inactieve postvak.
  
Als een bewaring al in een postvak is geplaatst of als er al een bewaarbeleid is toegepast op een postvak, hoeft u alleen het bijbehorende gebruikersaccount te verwijderen, zoals wordt uitgelegd in stap 2.
  
Zie het volgende voor stapsgewijs procedures voor het plaatsen van een postvak in De bewaring van rechtszaken of het toepassen van een bewaarbeleid:
  
- [Een postvak in de wacht houden voor rechtszaken plaatsen](create-a-litigation-hold.md)

- [Meer informatie over bewaarbeleid en bewaarlabels](retention.md)

> [!NOTE]
> Voor beleidsregels voor bewaring en bewaring van rechtszaken kunt u een bewaring voor onbepaalde tijd of een bewaring voor onbepaalde tijd maken. In een onbepaalde periode blijft de inhoud van het inactieve postvak voor altijd behouden, of totdat de wacht wordt verwijderd of totdat de duur van de wacht wordt gewijzigd. Nadat het bewaringsbeleid is verwijderd (ervan uitgaande dat het postvak meer dan 183 dagen geleden is verwijderd), wordt het inactieve postvak gemarkeerd voor permanent verwijderen en wordt de inhoud van het postvak niet meer bewaard of gedetecteerd. In een op tijd gebaseerd bewaringsbeleid of bewaarbeleid geeft u de duur van de bewaring op. Deze duur is per item en wordt berekend vanaf de datum waarop een postvakitem is ontvangen of gemaakt. Nadat de bewaring voor een postvakitem is verlopen en het item is verplaatst naar of zich bevindt in de map Herstelbare items in het inactieve postvak, wordt het item definitief verwijderd (verwijderd) uit het inactieve postvak nadat de bewaarperiode van het verwijderde item is verlopen. 
  
### <a name="step-2-delete-the-mailbox"></a>Stap 2: Het postvak verwijderen

Nadat het postvak in bewaring is geplaatst of er een bewaarbeleid op is toegepast, is de volgende stap het verwijderen van het postvak. De beste manier om een postvak te verwijderen, is door het bijbehorende gebruikersaccount in het Microsoft 365 verwijderen. Zie Een gebruiker verwijderen uit uw organisatie voor informatie over het verwijderen van [gebruikersaccounts.](../admin/add-users/delete-a-user.md)
  
> [!NOTE]
> U kunt het postvak  ook verwijderen met de cmdlet Postvak verwijderen in Exchange Online PowerShell. Zie Postvakken van gebruikers verwijderen [of herstellen in](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes)Exchange Online. 
  
## <a name="view-a-list-of-inactive-mailboxes"></a>Een lijst met inactieve postvakken weergeven

Een lijst met de inactieve postvakken in uw organisatie weergeven:

1. Ga naar <https://compliance.microsoft.com> en meld u aan met de referenties voor een beheerdersaccount in uw organisatie.

2. Klik in het linkernavigatiedeelvenster van het Microsoft 365 compliancecentrum op Alles weergeven **en** klik vervolgens op **Informatiebeheer > Bewaring.**

   ![Klik op de knop Inactief postvak op de pagina Bewaring](../media/MCCInactiveMailboxes1.png)

3. Klik op **de** pagina Bewaar op **Inactief postvak** om een lijst met inactieve postvakken weer te geven.

4. Selecteer een inactief postvak om een flyoutpagina weer te geven met informatie over het inactieve postvak.

   ![Op de flyoutpagina worden details weergegeven over het inactieve postvak](../media/MCCInactiveMailboxes2.png)  

U kunt op Pictogram Zoekresultaten exporteren klikken Exporteren om een CSV-bestand weer te geven of te downloaden dat aanvullende informatie bevat over ![ ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)  de inactieve postvakken in uw organisatie.

U kunt ook de volgende opdracht uitvoeren in Exchange Online PowerShell om de lijst met inactieve postvakken weer te geven.

```powershell
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

U kunt ook de volgende opdracht uitvoeren om de lijst met inactieve postvakken en andere informatie te exporteren naar een CSV-bestand. In dit voorbeeld wordt het CSV-bestand gemaakt in de huidige adreslijst.

```powershell
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```

> [!NOTE]
> Het is mogelijk dat een inactief postvak hetzelfde SMTP-adres heeft als een actief gebruikerspostvak. In dit geval kan de waarde van de **eigenschap DistinguishedName** of **ExchangeGuid** worden gebruikt om een inactief postvak uniek te identificeren.
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>De inhoud van een inactief postvak zoeken en exporteren

U hebt toegang tot de inhoud van het inactieve postvak met behulp van het hulpprogramma Inhoud zoeken in & Compliancecentrum. Wanneer u in een inactief postvak zoekt, kunt u een trefwoordzoekquery maken om naar specifieke items te zoeken of u kunt de volledige inhoud van het inactieve postvak retourneren. U kunt een voorbeeld van de zoekresultaten bekijken of de zoekresultaten exporteren naar een Outlook-bestand (PST) of als afzonderlijke e-mailberichten. Zie de volgende onderwerpen voor stapsgewijs procedures voor het zoeken naar postvakken en het exporteren van zoekresultaten:
  
- [Inhoud zoeken](content-search.md)

- [Zoekresultaten exporteren](export-search-results.md)

Hier zijn een paar dingen waar u rekening mee moet houden bij het zoeken naar inactieve postvakken.
  
- Als een inhoudszoekactie een gebruikerspostvak bevat en dat postvak inactief is gemaakt, blijft de inhoudszoekactie het inactieve postvak doorzoeken wanneer u de zoekopdracht opnieuw uitzoekt nadat deze inactief is.

- In sommige gevallen heeft een gebruiker mogelijk een actief postvak en een inactief postvak met hetzelfde SMTP-adres. In dit geval wordt alleen gezocht naar het specifieke postvak dat u selecteert als locatie voor een inhoudszoekactie. Met andere woorden: als u het postvak van een gebruiker toevoegt aan een zoekopdracht, kunt u er niet van uitgaan dat zowel de actieve als de inactieve postvakken worden doorzocht. alleen het postvak dat u expliciet aan de zoekopdracht toevoegt, wordt doorzocht.

- We raden u ten zeerste aan geen actief postvak en inactief postvak met hetzelfde SMTP-adres te hebben. Als u het SMTP-adres dat momenteel is toegewezen aan een inactief postvak opnieuw moet gebruiken, raden we u aan het inactieve postvak te herstellen of de inhoud van een inactief postvak te herstellen naar een actief postvak (of het archief van een actief postvak) en het inactieve postvak te verwijderen.

## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>De duur van bewaring van een inactief postvak wijzigen

Nadat een postvak inactief is gemaakt, kunt u de duur van de bewaring of het bewaarbeleid wijzigen dat is toegepast op het inactieve postvak. Zie De duur van de wacht voor een inactief postvak wijzigen in Office 365 voor [stapsgewijse procedures.](change-the-hold-duration-for-an-inactive-mailbox.md)
  
## <a name="recover-an-inactive-mailbox"></a>Een inactief postvak herstellen

Als een voormalige werknemer terugkeert naar uw organisatie of als een nieuwe werknemer wordt aangenomen om de taaktaken van de overleden werknemer op zich te nemen, kunt u de inhoud van het inactieve postvak herstellen. Wanneer u een inactief postvak herstelt, wordt het postvak geconverteerd naar een nieuw postvak, blijven de inhoud en mapstructuur van het inactieve postvak behouden en is het postvak gekoppeld aan een nieuw gebruikersaccount. Nadat het is hersteld, bestaat het inactieve postvak niet meer. Zie Een inactief postvak herstellen in Office 365 voor stapsgewijs procedures en meer informatie over het herstellen van een [inactief postvak.](recover-an-inactive-mailbox.md)
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>De inhoud van een inactief postvak herstellen naar een ander postvak

Als een andere werknemer de taakverantwoordelijkheden van een voormalige werknemer op zich neemt of als een andere persoon toegang nodig heeft tot de inhoud van het inactieve postvak, kunt u de inhoud van het inactieve postvak herstellen (of samenvoegen) naar een bestaand postvak. Wanneer u een inactief postvak herstelt, wordt de inhoud gekopieerd naar een ander postvak. Het inactieve postvak blijft behouden en blijft een inactief postvak. Het inactieve postvak kan nog steeds worden doorzocht met eDiscovery, de inhoud ervan kan worden hersteld naar een ander postvak of op een later tijdstip worden hersteld of verwijderd. Zie Een inactief postvak herstellen in Office 365 voor [stapsgewijse procedures.](restore-an-inactive-mailbox.md)
  
## <a name="delete-an-inactive-mailbox"></a>Een inactief postvak verwijderen

Als u de inhoud van een inactief postvak niet meer hoeft te behouden, kunt u het inactieve postvak permanent verwijderen door de bewaring te verwijderen of het bewaarbeleid te verwijderen dat is toegepast op het inactieve postvak. Het postvak blijft 183 dagen behouden nadat u het bewaar- of bewaringsbeleid hebt verwijderd. Na 183 dagen wordt het postvak gemarkeerd voor permanente verwijdering en kan het postvak niet meer worden hersteld. Als het inactieve postvak binnen de laatste 183 dagen is verwijderd, kunt u het nog steeds herstellen. Zie Een inactief postvak verwijderen voor stapsgewijs procedures voor het verwijderen van een bewarings- of bewaarbeleid voor het permanent verwijderen van een [inactief postvak.](delete-an-inactive-mailbox.md)
