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
description: Informatie over het upgraden van een of meer distributielijsten naar Microsoft 365 Groepen in Outlook en het gebruik van PowerShell om verschillende distributielijsten tegelijk te upgraden.
ms.openlocfilehash: 95f887b4386b349dc9d8bb471deab19b5425f6f5
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080525"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Distributielijsten upgraden naar Microsoft 365-groepen in Outlook

U kunt distributielijsten upgraden naar Microsoft 365 Groepen met Outlook. Dit is een goede manier om de distributielijsten van uw organisatie alle functies en functionaliteit van Microsoft 365 Groepen te geven. [Waarom u uw distributielijsten moet upgraden naar groepen in Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

U kunt distributielijsten een voor een of allemaal tegelijk upgraden.

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Een of meer distributielijsten upgraden naar Microsoft 365-groepen in Outlook

U moet een globale beheerder of Exchange-beheerder zijn om een distributielijst te upgraden. Als u wilt upgraden naar Microsoft 365 Groepen, moet een distributiegroep een eigenaar met een postvak hebben.

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.

2. Ga in het Exchange-beheercentrum naar **Groepen** \> **geadresseerden.**<br/>U ziet een melding dat u distributielijsten (ook wel distributiegroepen **genoemd)** hebt die in aanmerking komen om te worden geüpgraded naar Microsoft 365 Groepen.<br/> ![Selecteer de knop Aan de slag](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Selecteer een of meer distributielijsten (ook wel een **distributiegroep** genoemd) op de pagina **groepen**.<br/>![Een distributiegroep selecteren](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Selecteer het upgradepictogram.<br/>![Pictogram Upgraden naar Microsoft 365 Groepen](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. Selecteer Ja in het informatievenster **om** de upgrade te bevestigen. Het proces begint meteen. Het proces kan enkele minuten of uren duren, afhankelijk van de grootte en het aantal url's dat u wilt upgraden.<br/>Als de distributielijst niet kan worden geüpgraded, wordt er een dialoogvenster geopend waarin dit wordt aangegeven. Zie [Welke distributielijsten kunnen niet worden geüpgraded?](#which-distribution-lists-cant-be-upgraded)

6. Als u meerdere distributielijsten wilt upgraden, gebruikt u de vervolgkeuzelijst om te filteren welke distributielijsten zijn geüpgraded. Als de lijst niet volledig is, wacht  u iets langer en selecteert u Vervolgens Vernieuwen om te zien wat is geüpgraded.<br/>Er wordt niet gemeld wanneer het upgradeproces is voltooid voor alle distributielijsten die u hebt geselecteerd. U kunt dit zien door te bekijken wat wordt weergegeven onder **Beschikbaar voor upgrade** of **Upgraded DLs** (Geüpgradede distributielijsten).

7. Als u een distributielijst voor upgraden hebt geselecteerd maar deze nog steeds wordt weergegeven op de pagina als Beschikbaar voor upgrade, is het upgraden van de distributielijst mislukt. Zie [Wat u moet doen als de upgrade niet werkt](#what-to-do-if-the-upgrade-doesnt-work).

> [!NOTE]
> Als u samenvattings-e-mails van de groep ontvangt, wordt er soms onderaan vermeld dat u distributielijsten waarvan u eigenaar bent, kunt upgraden. Zie [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) (Een groepsgesprek hebben in Outlook) voor meer informatie over samenvattings-e-mails.

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Wat u moet doen als de upgrade niet werkt

Distributielijsten die niet kunnen worden geüpgraded, blijven ongewijzigd.

Als een of meer **in aanmerking komende** distributielijsten niet kunnen worden geüpgraded, opent u een [ondersteuningsticket](../contact-support-for-business-products.md). Het probleem moet worden geëscaleerd naar het team Groups Engineering zodat zij kunnen uitzoeken wat het probleem is.

Het is mogelijk dat de distributielijst niet is geüpgraded vanwege een serviceonderbreking, maar dit is tamelijk onwaarschijnlijk. U kunt ook even wachten en vervolgens opnieuw proberen de distributielijst te upgraden.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>PowerShell gebruiken om diverse distributielijsten tegelijkertijd te upgraden

Als u een ervaren PowerShell-gebruiker bent, wilt u misschien PowerShell in plaats van de gebruikersinterface gebruiken. We hebben een reeks cmdlets die u kunt gebruiken om distributielijsten te upgraden. Zie hieronder.

### <a name="upgrade-a-single-dl"></a>Eén DL upgraden

Voer de volgende opdracht uit om één dl bij te upgraden:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

Als u bijvoorbeeld een upgrade wilt uitvoeren van een DLs met SMTP-adres dl1@contoso.com, kunt u de volgende opdracht uitvoeren:

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> U kunt ook één distributielijst upgraden naar een Microsoft 365-groep met behulp van de PowerShell-cmdlet [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379)

### <a name="upgrade-multiple-dls-in-a-batch"></a>Meerdere DLs in een batch upgraden

U kunt meerdere DLs ook als een batch doorgeven en deze samen bijwerken:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

Als u bijvoorbeeld vijf DLs wilt upgraden met EEN SMTP-adres en de volgende `dl1@contoso.com` `dl2@contoso.com` opdracht wilt `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` uitvoeren:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Alle in aanmerking komende DLs upgraden

Er zijn twee manieren waarop u alle in aanmerking komende url's kunt upgraden.

> [!NOTE]
> De Upgrade-DistributionGroup-cmdlet ontvangt geen gegevens van de pijplijn, om deze reden is het vereist dat de operator 'foreach-object' goed {} wordt uitgevoerd.

1. Haal de in aanmerking komende DLs in de tenant op en upgrade ze met de upgrade-opdracht:

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Krijg de lijst met alle DLs en upgrade alleen de in aanmerking komende DLs:

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Veelgestelde vragen over het upgraden van distributielijsten naar Microsoft 365 Groepen in Outlook

### <a name="which-distribution-lists-cant-be-upgraded"></a>Welke distributielijsten kunnen niet worden geüpgraded?

U kunt alleen in de cloud beheerde, eenvoudige, niet-geneste distributielijsten upgraden. De onderstaande tabel bevat distributielijsten die **NIET kunnen** worden geüpgraded.

|**Eigenschap**|**Komt in aanmerking?**|
|:-----|:-----|
|On-premises beheerde distributielijst.  <br/> |Nee  <br/> |
|Geneste distributielijsten De distributielijst heeft onderliggende groepen of is lid van een andere groep.  <br/> |Nee  <br/> |
|Distributielijsten met lid **RecipientTypeDetails anders** dan **UserMailbox,** **SharedMailbox,** **TeamMailbox,** **MailUser**  <br/> |Nee  <br/> |
|Distributielijst met meer dan 100 eigenaren  <br/> |Nee  <br/> |
|Distributielijst met alleen leden, maar geen eigenaar  <br/> |Nee  <br/> |
|Distributielijst met een alias met speciale tekens  <br/> |Nee  <br/> |
|Als de distributielijst als een doorstuuradres voor Gedeeld postvak is geconfigureerd  <br/> |Nee  <br/> |
|Als de dl deel uitmaakt van **de beperking van de afzender** in een andere dl.  <br/> |Nee  <br/> |
|Beveiligingsgroepen  <br/> |Nee  <br/> |
|Dynamische distributielijsten  <br/> |Nee  <br/> |
|Distributielijsten die zijn geconverteerd **naar RoomLists**  <br/> |Nee  <br/> |
|Distributielijsten waarbij **LidJoinRestriction** **en/of MemberDepartRestriction** is **gesloten**  <br/> |Nee  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>Controleren welke url's in aanmerking komen voor de upgrade

Als u wilt controleren of een dl wel of niet in aanmerking komt, kunt u de onderstaande opdracht uitvoeren:

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

Als u wilt controleren welke url's in aanmerking komen voor de upgrade, kunt u de volgende opdracht uitvoeren:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Wie kan de upgradescripts uitvoeren?

Personen met globale beheerders- of Exchange-beheerdersrechten.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Waarom wordt op het visitekaartje nog steeds een distributielijst weergegeven? Wat moet ik doen om te voorkomen dat een geüpgradede distributielijst wordt weergegeven in mijn lijst met automatische suggesties?

- Voor Outlook: wanneer iemand een e-mailbericht in Outlook probeert te verzenden door de naam van de Microsoft 365-groep na de migratie te typen, wordt de geadresseerde niet als groep, maar als distributielijst opgelost. Het visitekaartje van de geadresseerde wordt het visitekaartje van de distributielijsten. Dit wordt veroorzaakt door de cache met geadresseerden of de cache met bijnamen in Outlook. Het e-mailbericht wordt naar de groep verzonden, maar dit kan tot verwarring leiden bij de afzender.<br/>U kunt aan de hand van de stappen in het onderwerp [Informatie over de lijst AutoAanvullen in Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) de cache opnieuw instellen om het probleem op te lossen.

- Voor de webversie van Outlook: In de webversie van Outlook blijft de ontvanger van de distributielijst in de cache staan. Volg de stappen in Voorgestelde naam of [e-mailadres](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) verwijderen uit de lijst voor automatisch voltooien om de cache te vernieuwen en het visitekaartje van de groep weer te geven.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>Krijgen nieuwe groepsleden een welkomstbericht in hun postvak IN?

Nee. De instelling voor het inschakelen van welkomstberichten is standaard ingesteld op onwaar. Deze instelling geldt voor zowel bestaande als nieuwe groepsleden die kunnen deelnemen nadat de migratie is voltooid. Als de groepseigenaar later gastgebruikers toestaat, ontvangen gastgebruikers geen welkomstbericht in hun postvak IN. Gastleden kunnen het werken met de groep voortzetten.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>Wat gebeurt er als een of meer van de DLs niet worden geüpgraded?

Er zijn enkele gevallen waarin dl wel in aanmerking komt, maar niet kan worden geüpgraded. De dl wordt niet geüpgraded en blijft een dl.

- Wanneer de beheerder **groepsbeleid** voor e-mailadres van de groep heeft toegepast voor de groepen in een organisatie en een upgrade van DLs probeert uit te voeren die niet voldoet aan de criteria, wordt de dl niet geüpgraded

- DLs met **MemberJoinRestriction** **of MemberDepartRestriction set to** **Closed,** could not be upgraded

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>Wat gebeurt er met de distributielijst als de upgrade vanuit het Exchange-beheercentrum mislukt?

De upgrade vindt alleen plaats als de oproep naar de server wordt verzonden. Als de upgrade mislukt, worden de distributielijsten niet gewijzigd. Ze blijven op dezelfde manier werken.
