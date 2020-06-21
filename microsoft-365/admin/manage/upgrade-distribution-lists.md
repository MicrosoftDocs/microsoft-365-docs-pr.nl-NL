---
title: Distributielijsten upgraden naar Microsoft 365-groepen in Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
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
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Meer informatie over het upgraden van een of meerdere distributielijsten naar Microsoft 365-groepen in Outlook en hoe u PowerShell gebruiken om meerdere distributielijsten tegelijk te upgraden.
ms.openlocfilehash: f5748c293d18943c94c3610c0e3c5c33848eb521
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780023"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Distributielijsten upgraden naar Microsoft 365-groepen in Outlook

U distributielijsten upgraden naar Microsoft 365-groepen met Outlook. Dit is een geweldige manier om de distributielijsten van uw organisatie alle functies en functionaliteit van Microsoft 365-groepen te geven. [Waarom u een upgrade voor uw distributielijsten moet uitvoeren naar groepen in Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

U kunt distributielijsten een voor een of allemaal tegelijk upgraden.

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Een of meer distributielijsten upgraden naar Microsoft 365-groepen in Outlook

U moet een globale beheerder of Exchange-beheerder zijn om een distributielijst te upgraden. Als u wilt upgraden naar Microsoft 365-groepen, moet een distributiegroep een eigenaar met een postvak hebben. 

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.

2. Ga in het Exchange-beheercentrum naar **Groepen ontvangers** \> **Groups**.<br/>U ziet een bericht waarin wordt aangegeven dat u distributielijsten hebt (ook wel **distributiegroepen** genoemd) die in aanmerking komen voor een upgrade naar Microsoft 365-groepen.<br/> ![De knop Aan de slag selecteren](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Selecteer een of meer distributielijsten (ook wel een **distributiegroep** genoemd) op de pagina **groepen**.<br/>![Een distributiegroep selecteren](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Selecteer het upgradepictogram.<br/>![Upgraden naar pictogram Microsoft 365-groepen](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. Selecteer in het **informatiedialoogvenster Ja** om de upgrade te bevestigen. Het proces begint onmiddellijk. Afhankelijk van de grootte en het aantal DLs dat u upgradet, kan het proces minuten of uren duren.<br/>Als de distributielijst niet kan worden geüpgraded, wordt er een dialoogvenster geopend waarin dit wordt aangegeven. Zie [Welke distributielijsten niet kunnen worden geüpgraded?](#which-distribution-lists-cannot-be-upgraded).

6. Als u meerdere distributielijsten upgradet, gebruikt u de vervolgkeuzelijst om te filteren welke distributielijsten zijn bijgewerkt. Als de lijst niet is voltooid, wacht u nog even en selecteert u **Vernieuwen** om te zien wat er is bijgewerkt.<br/>There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.

7. If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade. See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).

> [!NOTE]
> If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Wat u moet doen als de upgrade niet werkt

Distributielijsten die niet kunnen worden geüpgraded, blijven ongewijzigd.

If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.

It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely. If you want, wait a while and then try to upgrade the DL again.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>PowerShell gebruiken om diverse distributielijsten tegelijkertijd te upgraden

Als u een ervaren PowerShell-gebruiker bent, wilt u misschien PowerShell in plaats van de gebruikersinterface gebruiken. We hebben een set cmdlets die u zullen helpen bij het upgraden van distributielijsten. Zie hieronder.

### <a name="upgrade-a-single-dl"></a>Eén DL upgraden

Als u één DL wilt upgraden, voert u de volgende opdracht uit:

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

Als u bijvoorbeeld een DL's wilt upgraden met dl1@contoso.com SMTP-adres, voert u de volgende opdracht uit:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> U ook één distributielijst upgraden naar een Microsoft 365-groep met de [PowerShell-cmdlet New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379)

### <a name="upgrade-multiple-dls-in-a-batch"></a>Meerdere DLs in een batch upgraden

U ook meerdere DLs als batch doorgeven en samen upgraden:

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

Als u bijvoorbeeld vijf DLs wilt upgraden met smtp-adres `dl1@contoso.com` en de volgende opdracht wilt uitvoeren en de volgende opdracht wilt `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` uitvoeren:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Alle in aanmerking komende DLs upgraden

Er zijn twee manieren waarop u alle in aanmerking komende DLs upgraden.

> [!NOTE]
> De cmdlet Upgrade-DistributionGroup ontvangt geen gegevens uit de pijplijn, daarom is het nodig om de operator 'foreach-object' te gebruiken {} om succesvol uit te voeren.

1. Haal de in aanmerking komende DLs in de tenant en upgrade ze met de upgradeopdracht:

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Download de lijst met alle DL's en upgrade alleen de in aanmerking komende DLs:

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Veelgestelde vragen over het upgraden van distributielijsten naar Microsoft 365-groepen in Outlook

### <a name="which-distribution-lists-cannot-be-upgraded"></a>Welke distributielijsten kunnen niet worden geüpgraded?

U kunt alleen in de cloud beheerde, eenvoudige, niet-geneste distributielijsten upgraden. In de onderstaande tabel worden distributielijsten weergegeven die **NIET kunnen** worden bijgewerkt.

|**Eigenschap**|**Komt in aanmerking?**|
|:-----|:-----|
|On-premises beheerde distributielijst.  <br/> |Nee  <br/> |
|Nested distribution lists. Distribution list either has child groups or is a member of another group.  <br/> |Nee  <br/> |
|Distributielijsten met lid **RecipientTypeDetails,** met uitzondering **van UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**  <br/> |Nee  <br/> |
|Distributielijst met meer dan 100 eigenaren  <br/> |Nee  <br/> |
|Distributielijst met alleen leden, maar geen eigenaar  <br/> |Nee  <br/> |
|Distributielijst met een alias met speciale tekens  <br/> |Nee  <br/> |
|Als de distributielijst als een doorstuuradres voor Gedeeld postvak is geconfigureerd  <br/> |Nee  <br/> |
|Als de DL deel uitmaakt van **Sender Restriction** in een andere DL.  <br/> |Nee  <br/> |
|Beveiligingsgroepen  <br/> |Nee  <br/> |
|Dynamische distributielijsten  <br/> |Nee  <br/> |
|Distributielijsten die zijn geconverteerd naar **RoomLists**  <br/> |Nee  <br/> |
|Distributielijsten waarin **MemberJoinRestriction** en/of **MemberDepartRestriction** **gesloten** zijn  <br/> |Nee  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a>Hoe controleer ik welke DLs in aanmerking komen voor een upgrade?

Als u wilt controleren of een DL in aanmerking komt of niet, u de onderstaande opdracht uitvoeren:

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

Als u wilt controleren welke DLs in aanmerking komen voor een upgrade, voert u de volgende opdracht uit:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Wie kan de upgradescripts uitvoeren?

Mensen met algemene beheerders- of Exchange-beheerdersrechten.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Waarom wordt op het visitekaartje nog steeds een distributielijst weergegeven? Wat moet ik doen om te voorkomen dat een geüpgradede distributielijst wordt weergegeven in mijn lijst met automatische suggesties?

- Voor Outlook: Wanneer iemand een e-mail probeert te verzenden in Outlook door de naam van de Microsoft 365-groep na migratie te typen, wordt de ontvanger opgelost als de distributielijst in plaats van de groep. Het visitekaartje van de geadresseerde wordt het visitekaartje van de distributielijsten. Dit wordt veroorzaakt door de cache met geadresseerden of de cache met bijnamen in Outlook. De e-mail wordt met succes naar de groep verzonden, maar kan verwarring veroorzaken bij de afzender.<br/>U kunt aan de hand van de stappen in het onderwerp [Informatie over de lijst AutoAanvullen in Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) de cache opnieuw instellen om het probleem op te lossen.

- Voor de webversie van Outlook: In het geval van de webversie van Outlook blijft de ontvanger van de distributielijst nog steeds in de cache. U de stappen in [De voorgestelde naam of het e-mailadres verwijderen uit de lijst Automatisch aanvullen](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) volgen om de cache te vernieuwen om het groepscontactkaart te bekijken.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>Krijgen nieuwe groepsleden een welkomstbericht in hun postvak IN?

No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>Wat als een of meer van de DLs niet worden geüpgraded?

Er zijn enkele gevallen waarin DL wel in aanmerking komt, maar niet kan worden geüpgraded. De DL krijgt geen upgrade en blijft als een DL.

- Wanneer de beheerder **het groepse-adresbeleid** voor de groepen in een organisatie heeft toegepast en ze dls proberen te upgraden die niet aan de criteria voldoen, wordt de DL niet geüpgraded

- DL's met **MemberJoinRestriction** of **MemberDepartRestriction** ingesteld op **Gesloten**, kan niet worden opgewaardeerd

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>Wat gebeurt er met de distributielijst als de upgrade vanuit het Exchange-beheercentrum mislukt?

The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.


