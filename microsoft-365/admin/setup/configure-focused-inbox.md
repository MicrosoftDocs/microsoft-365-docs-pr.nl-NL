---
title: Postvak IN met prioriteit configureren voor iedereen in uw organisatie
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: Als u verantwoordelijk bent voor het configureren van e-mailinstellingen voor iedereen in een bedrijf, wordt in dit artikel uitgelegd hoe u Postvak IN met focus configureert voor gebruikers.
ms.openlocfilehash: ddd0886988072139a199bfc3f6e8adbbf25ad58b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623699"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>Postvak IN met prioriteit configureren voor iedereen in uw organisatie

Als u voor iedereen in uw bedrijf moet configureren hoe e-mail wordt gebruikt, is dit artikel interessant voor u. Er wordt uitgelegd hoe u dit kunt aanpassen of kunt uitschakelen voor uw bedrijf, en u krijgt antwoord op [Veelgestelde vragen](#faq-for-focused-inbox).

Zie [Postvak IN met prioriteit uitschakelen](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2) als u Postvak IN met prioriteit alleen voor uzelf wilt uitschakelen.  

Als u er zeker van wilt zijn dat uw gebruikers bepaalde zakelijke e-mailberichten ontvangen, bijvoorbeeld van de afdeling HR of de salarisadministratie, kunt u Postvak IN met prioriteit configureren zodat deze specifieke zakelijke e-mail met prioriteit wordt weergegeven. U kunt ook bepalen of gebruikers in uw organisatie Postvak IN met prioriteit zien in hun postvak.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>Postvak IN met prioriteit in- of uitschakelen in uw organisatie

U kunt Windows PowerShell gebruiken om Postvak IN met prioriteit voor iedereen in uw organisatie in of uit te schakelen. Wilt u dit doen in het Microsoft 365-beheercentrum? Laat het weten aan ons technische team. **[Stem hier!](https://go.microsoft.com/fwlink/?linkid=862489)**
  
**Postvak IN met prioriteit uitschakelen:**
  
Het volgende PowerShell-voorbeeld schakelt Postvak IN met prioriteit **uit** in uw organisatie. De functie blijft echter wel beschikbaar voor uw gebruikers, wat betekent dat ze Postvak IN met prioriteit desgewenst weer kunnen inschakelen in een e-mailclient. 
  
1. [Maak verbinding met Exchange Online via externe PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie voor meer informatie het item Transport rules (Transportregels) in [Messaging policy and compliance permissions](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help) (Machtigingen voor berichtenbeleid en naleving).

3. Voer de cmdlet **Get-OrganizationConfig** uit. 

    ```powershell
    Get-OrganizationConfig
    ```

4. Zoek naar **FocusedInboxOn** en bekijk de huidige instelling: 

    ![Antwoord van PowerShell op de status van het Postvak IN met prioriteit.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Voer de volgende cmdlet uit om Postvak IN met prioriteit uit te schakelen.

    ```powershell
    Set-OrganizationConfig -FocusedInboxOn $false
    ```

6. Voer de cmdlet **Get-OrganizationConfig** opnieuw uit. FocusedInboxOn staat nu ingesteld op $false, wat betekent dat het is uitgeschakeld. 

**Postvak IN met prioriteit inschakelen:**
  
- Voer in stap 5 hierboven de volgende cmdlet uit om Postvak IN met prioriteit in te schakelen.

  ```powershell
  Set-OrganizationConfig -FocusedInboxOn $true
  ```
    
## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>Wat zien gebruikers nadat ik Postvak IN met prioriteit inschakel? 

Gebruikers zien de weergave Prioriteit pas nadat ze Outlook opnieuw hebben gestart. Wanneer ze Outlook opnieuw hebben gestart, zien ze een Tip in de Outlook-gebruikersinterface met de optie om het nieuwe Postvak IN met prioriteit te gebruiken.
  
![Een afbeelding van hoe Postvak IN met prioriteit eruitziet als een gebruiker de webversie van Outlook voor het eerst opent.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
Als u van de functie Onbelangrijke e-mail overstapt op Postvak IN met prioriteit, kunnen zij deze inschakelen ('Probeer het') of de functie sluiten. Als de gebruiker meerdere (ondersteunde) clients heeft, kan hij voor elke client Postvak IN met prioriteit afzonderlijk in-of uitschakelen. De tip ziet er zo uit:
  
![Een afbeelding van hoe een Postvak IN met prioriteit eruitziet als deze is uitgerold voor uw gebruikers en Outlook opnieuw wordt geopend.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
Wanneer een gebruiker besluit Postvak IN met prioriteit te gaan gebruiken, wordt Onbelangrijke e-mail automatisch uitgeschakeld. De map Onbelangrijke e-mail wordt geconverteerd naar een standaardmap. De gebruiker kan deze map een andere naam geven of verwijderen.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>Postvak IN met prioriteit in- of uitschakelen voor specifieke gebruikers

In dit voorbeeld wordt Postvak IN met prioriteit **uitgeschakeld** voor Tim Matthews in de organisatie Contoso. De functie blijft echter wel beschikbaar voor hem. Als hij wil, kan hij Postvak IN met prioriteit weer inschakelen op elk van zijn clients. 
  
1. [Maak verbinding met Exchange Online via externe PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie voor meer informatie het item Transport rules (Transportregels) in het artikel Messaging policy and compliance permissions (Machtigingen voor berichtenbeleid en naleving).

3. Voer de cmdlet **Get-FocusedInbox** uit, bijvoorbeeld: 

    ```powershell
    Get-FocusedInbox -Identity <tim@contoso.com>
    ```

4. Zoek naar FocusedInboxOn en bekijk de huidige instelling:

    ![Antwoord van PowerShell op de status van het Postvak IN met prioriteit.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Voer de volgende cmdlet uit om Postvak IN met prioriteit uit te schakelen:

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
    ```

    Of voer de volgende cmdlet uit om het in te schakelen:

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
    ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>De gebruikersinterface gebruiken om een transportregel te maken om e-mailberichten voor alle gebruikers met prioriteit weer te geven

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.

2. Ga naar **E-mailstroom** \> **Regels**. Selecteer ![SBV-pictogram toevoegen](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) en selecteer vervolgens **Een nieuwe regel maken...**. 

3. Wanneer u klaar bent met het maken van een nieuwe regel, klikt u op **Opslaan** om de regel toe te passen.

    In de volgende afbeelding wordt een voorbeeld weergegeven waarbij alle berichten van 'Salarisadministratie' worden afgeleverd in Postvak IN met prioriteit.

    ![postvakinmetprioriteit salarisadministratie](../../media/focusedinbox-transport-rule.PNG)

    > [!NOTE]
    > De waardetekst van de berichtkop in dit voorbeeld is **X-MS-Exchange-Organization-BypassFocusedInbox**.
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Windows PowerShell gebruiken om een transportregel te maken om e-mailberichten voor alle gebruikers met prioriteit weer te geven

1. [Maak verbinding met Exchange Online via externe PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie voor meer informatie het item Transport rules (Transportregels) in [Messaging policy and compliance permissions](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help) (Machtigingen voor berichtenbeleid en naleving).

3. Voer de volgende opdracht uit om alle berichten van bijvoorbeeld 'Salarisadministratie' at te leveren in Postvak IN met prioriteit.

    ```powershell
    New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
    ```

> [!IMPORTANT]
> In dit voorbeeld zijn zowel 'X-MS-Exchange-Organization-BypassFocusedInbox' als 'true' hoofdlettergevoelig.
> De functie Postvak IN met prioriteit ondersteunt X-header die Onbelangrijke e-mail vermijdt. Als u deze instelling gebruikt in Onbelangrijke e-mail, wordt deze ook gebruikt in Postvak IN met prioriteit. Zie [Nieuwe-Transportregel](/powershell/module/exchange/new-transportrule) voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="how-do-you-know-this-worked"></a>Hoe weet u of dit heeft gewerkt?

U kunt de koptekst van e-mailberichten controleren om te kijken of de e-mailberichten door toepassing van een transportregel zijn bezorgd in Postvak IN met prioriteit. Kies een e-mailbericht in een postvak in uw organisatie waarop een transportregel voor Postvak IN met prioriteit is toegepast. Kijk of in de koptekst de tekst **X-MS-Exchange-Organization-BypassFocusedInbox: true** voorkomt. De regel werkt als dit het geval is. Zie het artikel[Koptekstgegevens weergeven voor een e-mailbericht](https://go.microsoft.com/fwlink/p/?LinkId=822530) voor instructies voor het vinden van de koptekstgegevens van een bericht.

### <a name="what-will-the-user-see"></a>Wat ziet de gebruiker?

Als er een transportregel is, wordt een melding weergegeven voor het overschrijven. In de webversie van Outlook wordt 'Altijd verplaatsen naar Overige' uitgeschakeld en wordt knopinfo weergeven. Outlook-clients op desktop maken het mogelijk om 'Altijd verplaatsen naar Overige' te selecteren en geven een dialoogvenster weer.

## <a name="turn-onoff-clutter"></a>Onbelangrijke e-mail in- of uitschakelen

We hebben meldingen ontvangen dat de functie Onbelangrijke e-mail voor sommige gebruikers plotseling niet meer werkt. Als dit gebeurt, kunt u deze functie weer inschakelen voor specifieke gebruikers. Zie [Onbelangrijke e-mail configureren voor uw organisatie](../email/configure-clutter.md).

## <a name="faq-for-focused-inbox"></a>Veelgestelde vragen over Postvak IN met prioriteit

Hier vindt u antwoorden op Veelgestelde vragen over Postvak IN met prioriteit.

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>Kan ik bepalen op welke manier ik de functie Postvak IN met prioriteit implementeer in mijn organisatie?

Ja. U kunt Postvak IN met prioriteit in- of uitschakelen voor de hele organisatie, of voor bepaalde gebruikers. Zie het bovenstaande.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>Is de functie Postvak IN met prioriteit alleen beschikbaar voor clients met Office 2016?

Ja, dit geldt alleen voor gebruikers met Office 2016. De functie wordt niet ondersteund voor Outlook 2013 of eerder.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>Hoe lang het duurt voordat de gewijzigde instelling van Postvak IN met prioriteit wordt doorgevoerd in Outlook?

Nadat u Postvak IN met prioriteit hebt in- of uitgeschakeld, wordt de nieuwe instelling van kracht op het moment dat uw gebruikers hun exemplaar van Outlook sluiten en opnieuw starten.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>Wat gebeurt er met de functie Onbelangrijke e-mail als ik Postvak IN met prioriteit inschakel?

Nadat u bent overgestapt, ontvangt u de e-mails waarvoor niet direct actie hoeft te worden ondernomen niet meer in de map Onbelangrijke e-mail. In plaats daarvan worden de e-mails geplaatst in de tabbladen Prioriteit of Overige in het postvak. Het algoritme dat items naar de map Onbelangrijke e-mail verplaatste, werkt nu voor Postvak IN met prioriteit, dus alle e-mails die in Onbelangrijke e-mail werden geplaatst, gaan nu naar Overige. Alle berichten die al in de map Onbelangrijke e-mail zitten, blijven daar totdat u besluit ze te verwijderen of te verplaatsen.
  
Lees dit bericht van [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>Kan ik Onbelangrijke e-mail ingeschakeld laten voor gebruikers? Wat adviseert Microsoft als het gaat om de keuze tussen Onbelangrijke e-mail en Postvak IN met prioriteit?

Ja, u kunt de functie Onbelangrijke e-mail ingeschakeld laten en Postvak IN met prioriteit uitschakelen. Aangezien de functie Onbelangrijke e-mail uiteindelijk echter volledig wordt vervangen door Postvak IN met prioriteit, adviseren wij om nu over te stappen op Postvak IN met prioriteit. Raadpleeg het volgende blogbericht voor meer informatie over wanneer u Onbelangrijke e-mail in Exchange Online gebruikt: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448) (Update over Postvak IN met prioriteit en onze plannen voor Onbelangrijke e-mail).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>Moet ik Onbelangrijke e-mail uitschakelen voor mijn eindgebruikers als we iedereen gaan overzetten naar Postvak IN met prioriteit?

Nee. U kunt de cmdlet Set-Clutter gebruiken om de functie Onbelangrijke e-mail expliciet uit te schakelen voor een postvak. Het is dan wel zo dat berichten die eerder werden omgeleid naar de map Onbelangrijke e-mail, in het Postvak IN blijven staan en dat de eigenaar deze berichten handmatig moet verwerken totdat de client is geüpgraded naar een versie die ondersteuning biedt voor Postvak IN met prioriteit. Het is daarom beter om de functie Onbelangrijke e-mail pas uit te schakelen wanneer de geüpgrade clients beschikbaar zijn.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>Waarom zijn er twee verschillende cmdlets voor het beheren van Postvak IN met prioriteit?

Postvak IN met prioriteit kan op twee niveaus worden ingesteld.
  
- **Organisatieniveau**: status van Postvak IN met prioriteit en een bijbehorend tijdstempel van het laatste tijdstip van bijwerken.

- **Postvakniveau**: status van Postvak IN met prioriteit en een bijbehorend tijdstempel van het laatste tijdstip van bijwerken 

### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>Hoe wordt er door Outlook aan de hand van deze twee statuswaarden bepaald of de functie Postvak IN met prioriteit wordt gebruikt?

Dit wordt bepaald aan de hand van de cmdlet met de meest recente tijdstempel. Standaard zijn beide tijdstempels 'null' en in dit geval wordt de functie ingeschakeld.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>Waarom retourneert de cmdlet Get-FocusedInbox 'true' als ik Postvak IN met prioriteit heb uitgeschakeld in mijn organisatie?

Er zijn twee cmdlets voor het beheren van Postvak IN met prioriteit. Wanneer u Get-FocusedInbox uitvoert voor een postvak, wordt de status van de functie op het niveau van het postvak geretourneerd. De weergave in Outlook wordt gekozen op basis van de cmdlet waarvan de status het laatst is gewijzigd.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>Kan ik een script uitvoeren om te zien wie Postvak IN met prioriteit heeft ingeschakeld?

Nee, en dat is standaard. Postvak IN met prioriteit kan alleen aan de clientzijde worden ingeschakeld, dus via de cmdlet weet u alleen of het postvak van de gebruiker in aanmerking komt voor deze functie. Het is mogelijk de functie gelijktijdig in sommige clients in te schakelen en in andere uit te schakelen, bijvoorbeeld ingeschakeld in Outlook-app en Outlook Mobile, maar uitgeschakeld in de webversie van Outlook.

## <a name="related-content"></a>Verwante inhoud

[Onbelangrijke e-mail configureren voor uw organisatie](../email/configure-clutter.md) (artikel)\
[Gedeeld postvakinstellingen configureren](../email/configure-a-shared-mailbox.md) (artikel)\
[Handtekeningen en disclaimers maken](create-signatures-and-disclaimers.md) (video)
