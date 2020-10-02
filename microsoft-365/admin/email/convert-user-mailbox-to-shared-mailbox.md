---
title: Het postvak van een gebruiker converteren naar een gedeeld postvak
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Leer hoe u een privé postvak converteert naar een gedeeld postvak dat door meerdere gebruikers kan worden geopend. '
ms.openlocfilehash: 027236afb5a77e950083f254a154c491d6abc6ac
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341190"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Het postvak van een gebruiker converteren naar een gedeeld postvak

Wanneer u het postvak van een gebruiker converteert naar een gedeeld postvak, blijven alle bestaande e-mailberichten en de agenda behouden. Het is nu alleen een gedeeld postvak waartoe meerdere personen toegang hebben in plaats van één persoon. Op een latere datum kunt u een gedeeld postvak weer converteren naar een gebruikerspostvak (privé).

**Hier volgen enkele belangrijke zaken die u moet weten:**

- Het gebruikerspostvak waarnaar u een licentie converteert, moet een licentie zijn toegewezen voordat u deze converteert naar een gedeeld postvak. Anders wordt de optie om het postvak te converteren niet weergegeven. Als u de licentie hebt verwijderd, moet u deze opnieuw toevoegen om het postvak te kunnen converteren. Wanneer het postvak is geconverteerd naar een gedeeld postvak, kunt u de licentie weer verwijderen uit het gebruikersaccount.

- Gedeelde postvakken kunnen tot maximaal 50 GB aan gegevens bevatten zonder dat hieraan een licentie is toegewezen. Als u meer gegevens wilt opslaan, moet u een licentie aan het postvak toewijzen. Mogelijk moet u een reeks grote e-mailberichten (bijvoorbeeld berichten met bijlagen) uit het gedeelde postvak verwijderen, om het te verkleinen zodat u de licentie kunt verwijderen.

- Verwijder niet het account van de oude gebruiker. Dat hebt u nodig om het gedeelde postvak aan te verankeren. Als u het gebruikersaccount al hebt verwijderd, raadpleeg dan [Het postvak van een verwijderde gebruiker converteren](#convert-the-mailbox-of-a-deleted-user).

- De regels blijven ongewijzigd nadat het postvak is geconverteerd naar een gedeeld postvak.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Het Exchange-Beheercentrum gebruiken om een postvak te converteren
 
1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.

2. Selecteer **ontvangers** \> **postvakken**.

3. Selecteer het gebruikerspostvak. Selecteer **converteren**onder **converteren naar gedeeld postvak**.

4. Als het postvak kleiner is dan 50 GB, kunt u de [licentie van de gebruiker](../manage/remove-licenses-from-users.md)intrekken en geen betaling meer betalen. Verwijder niet het account van de gebruiker. Het gedeelde postvak moet blijven bestaan als anker. Als u het postvak wilt converteren van een werknemer die uw organisatie verlaat, moet u extra stappen uitvoeren om ervoor te zorgen dat ze niet meer kunnen worden aangemeld. Zie [een voormalige werknemer verwijderen uit Microsoft 365](../add-users/remove-former-employee.md).
    
> [!NOTE]
> Het is niet nodig om het wachtwoord van de gebruiker opnieuw in te stellen tijdens het converteren van het postvak. Als het wachtwoord echter niet opnieuw wordt ingesteld, **blijven de oorspronkelijke gebruikersnaam en het wachtwoord werken** na voltooiing van de Postvak conversie.

Voor alles wat u verder moet weten over gedeelde postvakken raadpleegt u [gedeelde postvakken](about-shared-mailboxes.md) en [Maak een gedeeld postvak](create-a-shared-mailbox.md).

> [!NOTE]
> Voor gedeelde postvakken is geen afzonderlijke licentie nodig. Als u echter in-place archief of een in-place bewaring of een in-place bewaring wilt inschakelen voor een gedeeld postvak, moet u een Exchange Online-abonnement 1 toewijzen met een licentie voor Exchange Online Archiving of Exchange Online plan 2 voor het postvak.


## <a name="convert-the-mailbox-of-a-deleted-user"></a>Het postvak van een verwijderde gebruiker converteren

Stel dat u een gebruikersaccount hebt verwijderd en nu het oude postvak van dat account wilt converteren naar een gedeeld postvak. Hier leest u wat u kunt doen:

1. [Herstel het account van de gebruiker](../add-users/restore-user.md).

2. Zorg ervoor dat er een Microsoft 365-licentie aan het account is toegewezen.

3. Het wachtwoord van de gebruiker opnieuw instellen.
    
4. Wacht twintig tot dertig minuten tot het postvak opnieuw is gemaakt.
    
5. Volg nu de instructies op deze pagina om het postvak te converteren naar een gedeeld postvak.
    
6. Wanneer u klaar bent, kunt u de licentie van het postvak van de gebruiker verwijderen. Verwijder het oude postvak van de gebruiker niet. Het gedeelde postvak moet blijven bestaan als anker.
    
7. Voeg leden toe aan het gedeeld postvak.


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Een gedeeld postvak weer converteren naar het persoonlijke postvak van een gebruiker

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.
   
2. Selecteer **Recipients** \> **gedeelde**geadresseerden.

3. Selecteer het gedeelde Postvak. Selecteer converteren **naar normaal postvak voor** **converteren**.

4. Ga terug naar het Beheercentrum. Kies onder **Gebruikers** het gebruikersaccount dat is gekoppeld aan het oude gedeeld postvak. Wijs een licentie toe aan het account en stel het wachtwoord opnieuw in.

   Het duurt enkele minuten voordat het postvak is ingesteld, maar daarna kan de persoon die dat account gaat gebruiken aan de slag. Wanneer deze gebruiker zich aanmeldt, worden de e-mail- en agenda-items weergegeven die anders in het gedeelde postvak stonden.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Het postvak van een gebruiker converteren in een hybride omgeving

Als dit gedeelde Postvak zich in een hybride omgeving bevindt, wordt u **ten zeerste aangeraden** (bijna verplicht!) u het gebruikerspostvak weer naar on-premises verplaatsen, het postvak van de gebruiker converteren naar een gedeeld postvak en het gedeelde Postvak vervolgens weer naar de Cloud verplaatsen. 

Ga als volgt te werk: als u het postvak in de Cloud converteert, kan het worden geconverteerd, maar on-premises is het postvak van de gebruiker, omdat de nieuwe realiteit geen keer wordt gesynchroniseerd op on-premises.

Dit is meestal niet het geval, maar er zijn een aantal scenario's waarin de on-premises kenmerken (waarmee het postvak van de gebruikerspostvak kan worden overschreven), de nieuwe Cloud versies van die kenmerken kunnen overzetten, en het postvak kan hierdoor worden geconverteerd. Dit is een probleem omdat gebruikerspostvakken licenties nodig hebben **of ze gedurende 30 dagen worden verwijderd**.

We hebben de meeste redenen besproken waarom dit gebeurt, maar het is wel zo vaak. U kunt het beste veilig zijn en het postvak weer naar on-premises verplaatsen, dit converteren en het gedeelde Postvak vervolgens weer naar de Cloud verplaatsen. Deze aanbevolen oplossing is niet in strijd met de licentieovereenkomst voor hybride omgevingen omdat het gebruik van de on-premises postvak van de gebruiker slechts tijdelijk is. Als u het postvak van de gebruiker of het gedeelde Postvak in uw on-premises organisatie onderneemt, krijgt u overtreding van uw licentie.

> [!NOTE]
> Als u lid bent van de rollen groep beheer van organisatie of geadresseerden, kunt u de Exchange-beheer shell gebruiken om een gebruikerspostvak te wijzigen in een gedeelde Postvak on-premises. Bijvoorbeeld `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.

> [!TIP]
> Zie de tijdelijke oplossing in deze ondersteunings oplossing voor gevallen waarin [gedeelde postvakken onverwacht worden geconverteerd naar postvakken van gebruikers](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).
  
## <a name="related-articles"></a>Verwante artikelen

[Meer over gedeelde postvakken](about-shared-mailboxes.md)

[Een gedeeld postvak maken](create-a-shared-mailbox.md)

[Een gedeeld postvak configureren](configure-a-shared-mailbox.md)

[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md)

[Problemen oplossen met gedeelde postvakken](resolve-issues-with-shared-mailboxes.md)
