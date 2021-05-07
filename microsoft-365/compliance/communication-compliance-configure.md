---
title: Aan de slag met communicatiecompliance
description: Beleidsregels voor communicatiecond compliance instellen om gebruikerscommunicatie te configureren voor controle.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 3e84c3266dd802fb6cab12db0c20773838b4e2a9
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2021
ms.locfileid: "52162775"
---
# <a name="get-started-with-communication-compliance"></a>Aan de slag met communicatiecompliance

Gebruik communicatie compliancebeleid om gebruikerscommunicatie te identificeren voor onderzoek door interne of externe revisoren. Zie communicatie compliancebeleid in Microsoft 365 voor meer informatie over hoe communicatie compliancebeleid u kan helpen bij het bewaken van communicatie [in uw organisatie.](communication-compliance.md) Als u wilt controleren hoe Contoso snel een compliancebeleid voor communicatie heeft geconfigureerd om te controleren op aanstootgevende taal in Microsoft Teams, Exchange Online en Yammer-communicatie, bekijkt u deze case [study.](communication-compliance-case-study.md)

## <a name="subscriptions-and-licensing"></a>Abonnementen en licenties

Voordat u aan de slag gaat met communicatie-compliance, moet u uw Microsoft 365 [en](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) eventuele invoegtoepassingen bevestigen. Als u communicatie compliance wilt openen en gebruiken, moet uw organisatie een van de volgende abonnementen of invoegtoepassingen hebben:

- Microsoft 365 E5 (betaalde of proefversie)
- Microsoft 365 E3 +de Microsoft 365 E5 Compliance-invoegvoegvoeging
- Microsoft 365 E3 abonnement + de Microsoft 365 E5 Insider Risk Management-invoegvoegvoeging
- Microsoft 365 A5-abonnement (betaalde versie of proefversie)
- Microsoft 365 A3-abonnement + de Microsoft 365 A5 Compliance-invoegvoegvoeging
- Microsoft 365 A3-abonnement + de Microsoft 365 A5 Insider Risk Management-invoegvoegvoeging
- Microsoft 365 G5-abonnement (betaalde versie of proefversie)
- Microsoft 365 G5-abonnement + de Microsoft 365 G5 Compliance-invoegvoegvoeging
- Microsoft 365 G5-abonnement + de Microsoft 365 G5 Insider Risk Management-invoegvoegvoeging
- Office 365 Enterprise E5-abonnement (betaalde of proefversie)
- Office 365 A5 (betaalde of proefversie)
- Office 365 Enterprise E3-abonnement + de Office 365 Advanced Compliance-invoegabonnement (niet meer beschikbaar voor nieuwe abonnementen, zie opmerking)

Gebruikers die deel uit maken van communicatie compliancebeleid, moeten een van de bovenstaande licenties krijgen toegewezen.

>[!IMPORTANT]
>Office 365 Advanced Compliance wordt niet meer als zelfstandig abonnement verkocht. Wanneer huidige abonnementen verlopen, moeten klanten overstappen op een van de bovenstaande abonnementen, die dezelfde of aanvullende compliancefuncties bevatten.

Als u geen bestaand Office 365 Enterprise E5-abonnement hebt en communicatie-compliance wilt proberen, kunt u [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) toevoegen aan uw bestaande abonnement [of](https://www.microsoft.com/microsoft-365/enterprise) u registreren voor een proefabonnement op Office 365 Enterprise E5.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Stap 1 (vereist): Machtigingen voor communicatie compliance inschakelen

>[!Important]
>Globale beheerders hebben standaard geen toegang tot communicatie-compliancefuncties. De rollen die in deze stap zijn toegewezen, zijn vereist voordat alle communicatie-compliancefuncties toegankelijk zijn. Nadat u de rollengroepen hebt geconfigureerd, kan het tot 30 minuten duren voordat de machtigingen voor rollengroepen van toepassing zijn op toegewezen gebruikers in uw organisatie.

Er zijn vijf rollengroepen die worden gebruikt om machtigingen te configureren voor het beheren van communicatie compliancefuncties. Als u **communicatie compliance** beschikbaar wilt maken als een menuoptie in Microsoft 365 compliancecentrum en als  u deze configuratiestappen wilt voortzetten, moet u zijn toegewezen aan de rollengroepen Communicatie compliance of *Communicatie compliancebeheerder.* Als u na de eerste configuratie communicatie compliancefuncties wilt openen en beheren, moeten gebruikers lid zijn van ten minste één rolgroep communicatie compliance.

Afhankelijk van hoe u communicatiebeleid en waarschuwingen wilt beheren, moet u gebruikers toewijzen aan specifieke rollengroepen. U hebt de optie om gebruikers met verschillende complianceverantwoordelijkheden toe te wijzen aan specifieke rollengroepen om verschillende gebieden met communicatie compliancefuncties te beheren. Of u kunt besluiten om alle gebruikersaccounts voor aangewezen beheerders, analisten, onderzoeker en kijkers toe te wijzen aan de *rollengroep Communicatie compliance.* Gebruik één rollengroep of meerdere rollengroepen om het best aan uw vereisten voor compliancebeheer te voldoen.

Kies uit deze opties voor rollengroep bij het configureren van communicatie compliance:

| Rol | Rolmachtigingen |
|:-----|:-----|
| **Naleving van communicatie** | Gebruik deze rollengroep om communicatie compliance voor uw organisatie in één groep te beheren. Door alle gebruikersaccounts toe te voegen voor aangewezen beheerders, analisten, onderzoeker en kijkers, kunt u communicatie compliancemachtigingen configureren in één groep. Deze rollengroep bevat alle machtigingsrollen voor communicatie compliance. Deze configuratie is de eenvoudigste manier om snel aan de slag te gaan met communicatie-compliance en is geschikt voor organisaties die geen afzonderlijke machtigingen nodig hebben die zijn gedefinieerd voor afzonderlijke groepen gebruikers. |
| **Communicatie compliancebeheerder** | Gebruik deze rollengroep om communicatie compliance in eerste instantie te configureren en later om beheerders van communicatie compliance te scheiden in een gedefinieerde groep. Gebruikers die aan deze rollengroep zijn toegewezen, kunnen communicatie compliancebeleid, globale instellingen en toewijzingen voor rollengroepen maken, lezen, bijwerken en verwijderen. Gebruikers die aan deze rollengroep zijn toegewezen, kunnen geen berichtwaarschuwingen weergeven. |
| **Communicatie compliance-analist** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als communicatie-complianceanalisten. Gebruikers die aan deze rollengroep zijn toegewezen, kunnen beleid weergeven waarin ze zijn toegewezen als revisoren, metagegevens van berichten weergeven (geen berichtinhoud), escaleren naar extra revisoren of meldingen verzenden naar gebruikers. Analisten kunnen waarschuwingen in behandeling niet oplossen. |
| **Communicatie compliance-onderzoeker** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die fungeren als communicatie compliance-onderzoeker. Gebruikers die aan deze rollengroep zijn toegewezen, kunnen metagegevens en inhoud van berichten bekijken, escaleren naar extra revisoren, escaleren naar een Advanced eDiscovery-geval, meldingen naar gebruikers verzenden en de waarschuwing oplossen. |
| **Viewer voor communicatie compliance** | Gebruik deze groep om machtigingen toe te wijzen aan gebruikers die communicatierapporten beheren. Gebruikers die aan deze rollengroep zijn toegewezen, hebben toegang tot alle rapportagewidgets op de startpagina communicatie compliance en kunnen alle communicatie compliancerapporten bekijken. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>Optie 1: Alle compliancegebruikers toewijzen aan de rollengroep Communicatie compliance

1. Meld u [https://protection.office.com/permissions](https://protection.office.com/permissions) aan bij het gebruik van referenties voor een beheerdersaccount in uw Microsoft 365 organisatie.

2. Ga in het &amp; Beveiligings compliancecentrum naar **Machtigingen.** Selecteer de koppeling voor het weergeven en beheren van rollen in Office 365.

3. Selecteer de *rollengroep Communicatie compliance* en selecteer **vervolgens Rollengroep bewerken.**

4. Selecteer **Leden kiezen** in het linkernavigatiedeelvenster en selecteer vervolgens **Bewerken.**

5. Selecteer **Toevoegen** en schakel het selectievakje in voor alle gebruikers die u wilt toevoegen aan de rollengroep *Communicatie compliance.*

6. Selecteer **Toevoegen** en selecteer vervolgens **Klaar.**

7. Selecteer **Opslaan om** de gebruikers toe te voegen aan de rollengroep. Selecteer **Sluiten om** de stappen uit te voeren

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>Optie 2: Gebruikers toewijzen aan specifieke rollengroepen voor communicatie compliance

Gebruik deze optie om gebruikers toe te wijzen aan specifieke rollengroepen om toegang tot communicatie compliance en verantwoordelijkheden tussen verschillende gebruikers in uw organisatie te segmenteren.

1. Meld u [https://protection.office.com/permissions](https://protection.office.com/permissions) aan bij het gebruik van referenties voor een beheerdersaccount in uw Microsoft 365 organisatie.

2. Ga in het &amp; Beveiligings compliancecentrum naar **Machtigingen.** Selecteer de koppeling voor het weergeven en beheren van rollen in Office 365.

3. Selecteer een van de rollengroepen voor communicatie compliance en selecteer **vervolgens Rollengroep bewerken.**

4. Selecteer **Leden kiezen** in het linkernavigatiedeelvenster en selecteer vervolgens **Bewerken.**

5. Selecteer **Toevoegen** en schakel het selectievakje in voor alle gebruikers die u wilt toevoegen aan de rollengroep.

6. Selecteer **Toevoegen** en selecteer vervolgens **Klaar.**

7. Selecteer **Opslaan om** de gebruikers toe te voegen aan de rollengroep.

8. Selecteer de volgende rollengroep communicatie compliance en herhaal stap 4-7 voor elke vereiste rollengroep.

9. Selecteer **Sluiten om** de stappen uit te voeren.

Zie Machtigingen in het Compliancecentrum voor meer informatie over rollengroepen en [machtigingen.](../security/office-365-security/protect-against-threats.md)

## <a name="step-2-required-enable-the-audit-log"></a>Stap 2 (vereist): Het auditlogboek inschakelen

Communicatie compliance vereist auditlogboeken om waarschuwingen weer te geven en herstelacties van revisoren bij te houden. De auditlogboeken zijn een overzicht van alle activiteiten die zijn gekoppeld aan een gedefinieerd organisatiebeleid of op elk moment dat een communicatiebeleid wordt gewijzigd.

Zie Zoeken in auditlogboek in- of uitschakelen voor stapsgewijs instructies voor het in- of [uitschakelen van controlelogboek.](turn-audit-log-search-on-or-off.md) Nadat u de controle hebt in- of uitgevoerd, wordt een bericht weergegeven met de melding dat het auditlogboek wordt voorbereid en dat u een zoekopdracht kunt uitvoeren binnen een paar uur nadat de voorbereiding is voltooid. U hoeft deze actie maar één keer uit te voeren. Zie Het auditlogboek doorzoeken voor meer informatie over het gebruik [van het auditlogboek.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Stap 3 (optioneel): Groepen instellen voor communicatie compliance

 Wanneer u een communicatie-compliancebeleid maakt, bepaalt u wie de communicatie heeft beoordeeld en wie beoordelingen uitvoert. In het beleid gebruikt u e-mailadressen om personen of groepen personen te identificeren. Als u de installatie wilt vereenvoudigen, kunt u groepen maken voor personen die hun communicatie hebben beoordeeld en groepen voor personen die deze communicatie bekijken. Als u groepen gebruikt, hebt u mogelijk meerdere groepen nodig. Als u bijvoorbeeld de communicatie tussen twee verschillende groepen personen wilt controleren of als u een groep wilt opgeven die niet wordt gecontroleerd.

Gebruik de volgende grafiek om groepen in uw organisatie te configureren voor communicatie compliancebeleid:

| **Beleidslid** | **Ondersteunde groepen** | **Niet-ondersteunde groepen** |
|:-----|:-----|:-----|
|Gecontroleerde gebruikers <br> Niet-gecontroleerde gebruikers | Distributiegroepen <br> Microsoft 365 Groepen | Dynamische distributiegroepen <br> Geneste distributiegroepen <br> Beveiligingsgroepen met e-mail <br> Microsoft 365 groepen met dynamisch lidmaatschap |
| Revisoren | Geen | Distributiegroepen <br> Dynamische distributiegroepen <br> Geneste distributiegroepen <br> Beveiligingsgroepen met e-mail |
  
Wanneer u een distributiegroep toewijst in het beleid, worden alle e-mailberichten en Teams van elke gebruiker in de distributiegroep bewaakt. Wanneer u een Microsoft 365 groep in het beleid toewijst, worden alle e-mailberichten en Teams-chats die naar die groep zijn verzonden, bewaakt door het beleid, niet de afzonderlijke e-mailberichten en chats die door elk groepslid zijn ontvangen.

Als u een organisatie bent met een on-premises implementatie Exchange een externe e-mailprovider en u Microsoft Teams-chats voor uw gebruikers wilt controleren, moet u een distributiegroep maken voor de gebruikers met on-premises of externe postvakken die u wilt controleren. Later in deze stappen wijst u deze  distributiegroep toe als de selectie onder toezicht van gebruikers en groepen in de beleidswizard.

Als u gecontroleerde gebruikers in grote ondernemingen wilt beheren, moet u mogelijk alle gebruikers in grote groepen controleren. U kunt PowerShell gebruiken om een distributiegroep te configureren voor een globaal communicatiebeleid voor de toegewezen groep. Op deze manier kunt u duizenden gebruikers met één beleid controleren en het communicatiebeleid bijgewerkt houden wanneer nieuwe werknemers lid worden van uw organisatie.

1. Maak een speciale [distributiegroep](/powershell/module/exchange/new-distributiongroup) voor uw wereldwijde communicatiebeleid met de volgende eigenschappen: Zorg ervoor dat deze distributiegroep niet wordt gebruikt voor andere doeleinden of andere Office 365 services.

    - **MemberDepartRestriction = Closed**. Zorgt ervoor dat gebruikers zichzelf niet kunnen verwijderen uit de distributiegroep.
    - **MemberJoinRestriction = Closed**. Zorgt ervoor dat gebruikers zichzelf niet kunnen toevoegen aan de distributiegroep.
    - **ModerationEnabled = Waar**. Zorgt ervoor dat alle berichten die naar deze groep worden verzonden, worden goedgekeurd en dat de groep niet wordt gebruikt om te communiceren buiten de configuratie van het communicatiebeleid.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Selecteer een ongebruikte [Exchange aangepast kenmerk om](/Exchange/recipients/mailbox-custom-attributes) gebruikers bij te houden die zijn toegevoegd aan het communicatie compliancebeleid in uw organisatie.

3. Voer het volgende PowerShell-script uit volgens een terugkerende planning om gebruikers toe te voegen aan het communicatie compliancebeleid:

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

Zie voor meer informatie over het instellen van groepen:

- [Distributiegroepen maken en beheren](/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Overzicht van Microsoft 365 groepen](/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Stap 4 (optioneel): Controleren of Yammer tenant zich in de standaardmodus

In de autochtone modus zijn alle Yammer gebruikers in Azure Active Directory (Azure AD), zijn alle groepen Office 365 Groepen en worden alle bestanden opgeslagen in SharePoint Online. Uw Yammer tenant moet in de autochtone modus zijn voor communicatiebeleid voor het scannen en identificeren van risicovolle gesprekken in privéberichten en communitygesprekken in Yammer.

Zie voor meer informatie over het configureren Yammer in de autochtone modus:

- [Overzicht van Yammer native modus in Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode)
- [Configureer Yammer netwerk voor Native Mode voor Microsoft 365](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Stap 5 (vereist): Een communicatie-compliancebeleid maken
  
>[!Important]
>Het gebruik van PowerShell voor het maken en beheren van communicatie compliancebeleid wordt niet ondersteund. Als u dit beleid wilt maken en beheren, moet u de besturingselementen voor beleidsbeheer gebruiken in [Microsoft 365 oplossing voor communicatie compliance.](https://compliance.microsoft.com/supervisoryreview)

1. Meld u [https://compliance.microsoft.com](https://compliance.microsoft.com) aan bij het gebruik van referenties voor een beheerdersaccount in uw Microsoft 365 organisatie.

2. Selecteer in Microsoft 365 compliancecentrum de optie **Communicatie compliance.**
  
3. Selecteer het **tabblad** Beleid.

4. Selecteer **Beleid maken** om een nieuw beleid te maken en te configureren op basis van een sjabloon of om een aangepast beleid te maken en te configureren.

    Als u een beleidssjabloon kiest om een beleid te maken, gaat u als volgende te werk:

    - Bevestig of werk de naam van het beleid bij. Beleidsnamen kunnen niet worden gewijzigd nadat het beleid is gemaakt.

    - Kies de gebruikers of groepen die u wilt controleren, inclusief het kiezen van gebruikers of groepen die u wilt uitsluiten. Wanneer u de sjabloon conflict of interest gebruikt, selecteert u twee groepen of twee gebruikers die u wilt controleren op interne communicatie.

    - Kies de revisoren voor het beleid. Revisoren zijn afzonderlijke gebruikers en alle revisoren moeten postvakken hebben die worden gehost op Exchange Online. Revisoren die hier zijn toegevoegd, zijn de revisoren waar u uit kunt kiezen bij het escaleren van een waarschuwing in de werkstroom voor onderzoek en herstel. Wanneer revisoren aan een beleid worden toegevoegd, ontvangen ze automatisch een e-mailbericht waarin ze worden op de hoogte gehouden van de toewijzing aan het beleid en koppelingen bevatten naar informatie over het revisieproces.

    - Kies een veld met beperkte voorwaarden, meestal een gevoelige informatietype of trefwoordwoordenlijst die u wilt toepassen op het beleid.

    >[!NOTE]
    >Als u [OCR (Optical Character Recognition)](communication-compliance-feature-reference.md#optical-character-recognition-ocr-preview) wilt inschakelen om ingesloten of bijgevoegde afbeeldingen in berichten te scannen op afgedrukte of handgeschreven tekst die aan de beleidsvoorwaarden voldoen, selecteert u Beleidsvoorwaarden en percentage aanpassen en selecteert u Afgedrukte of  >   **handgeschreven** tekst uit afbeeldingen extraheren voor evaluatie.

    Als u ervoor kiest om de wizard Beleid te gebruiken om een aangepast beleid te maken, gaat u als volgende te werk:

    - Geef het beleid een naam en beschrijving. Beleidsnamen kunnen niet worden gewijzigd nadat het beleid is gemaakt.

    - Kies de gebruikers of groepen die u wilt controleren, inclusief alle gebruikers in uw organisatie, specifieke gebruikers en groepen, of andere gebruikers en groepen die u wilt uitsluiten.

    - Kies de revisoren voor het beleid. Revisoren zijn afzonderlijke gebruikers en alle revisoren moeten postvakken hebben die worden gehost op Exchange Online. Revisoren die hier zijn toegevoegd, zijn de revisoren waar u uit kunt kiezen bij het escaleren van een waarschuwing in de werkstroom voor onderzoek en herstel. Wanneer revisoren aan een beleid worden toegevoegd, ontvangen ze automatisch een e-mailbericht waarin ze worden op de hoogte gehouden van de toewijzing aan het beleid en koppelingen bevatten naar informatie over het revisieproces.

    - Kies de communicatiekanalen die u wilt scannen, Exchange, Microsoft Teams, Yammer of Skype voor Bedrijven. U kiest er ook voor om bronnen van derden te scannen als u een connector hebt geconfigureerd in Microsoft 365.

    - Kies de communicatierichting die u wilt controleren, inclusief binnenkomende, uitgaande of interne communicatie.

    - De voorwaarden voor communicatie [compliancebeleid definiëren.](communication-compliance-feature-reference.md#ConditionalSettings) U kunt kiezen uit berichtadres, trefwoord, bestandstypen en maatcondities.

    - Kies of u gevoelige informatietypen wilt opnemen. In deze stap kunt u standaard- en aangepaste gevoelige informatietypen selecteren. Kies uit bestaande aangepaste gevoelige informatietypen of aangepaste trefwoordwoordenlijsten in de wizard Communicatie compliancebeleid. U kunt deze items maken voordat u de wizard indien nodig kunt uitvoeren. U kunt ook nieuwe typen gevoelige informatie maken vanuit de wizard communicatie compliancebeleid.

    - Kies of u classificaties wilt inschakelen. Classificaties kunnen ongepaste taal en afbeeldingen detecteren die zijn verzonden of ontvangen in de berichttekst van e-mailberichten of andere typen tekst. U kunt de volgende ingebouwde classificaties kiezen: *Bedreiging,* Godslastering, Gerichte *pesterijen,* Afbeeldingen voor *volwassenen,* Ijzige *afbeeldingen* en *Gory-afbeeldingen.*

    - Schakel [OCR (Optical Character Recognition)](communication-compliance-feature-reference.md#optical-character-recognition-ocr-preview) in om ingesloten of bijgevoegde afbeeldingen in berichten te scannen op afgedrukte of handgeschreven tekst die aan de beleidsvoorwaarden voldoen. Voor aangepast beleid moeten een of meer voorwaardelijke instellingen die zijn gekoppeld aan tekst, trefwoorden, classificaties of gevoelige informatietypen, zijn geconfigureerd in het beleid om het scannen van optische tekens te kunnen selecteren.

    - Definieer het percentage te controleren communicatie.

    - Bekijk uw beleidsselecties en maak het beleid.

5. Selecteer **Beleid maken** wanneer u de sjablonen gebruikt of **Verzenden** wanneer u de wizard Aangepast beleid gebruikt.

6. De **pagina Uw beleid is** gemaakt, wordt weergegeven met richtlijnen voor wanneer beleid wordt geactiveerd en welke communicatie wordt vastgelegd.

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a>Stap 6 (optioneel): Kennisgevingssjablonen maken en gebruikersanonimisatie configureren

Als u de optie wilt hebben om te reageren op een beleidsmelding door een herinneringsmelding te verzenden naar de gekoppelde gebruiker, moet u ten minste één kennisgevingssjabloon maken in uw organisatie. De velden met aankondigingssjabloon kunnen worden bewerkt voordat ze worden verzonden als onderdeel van het herstelproces voor waarschuwingen en het is raadzaam een aangepaste kennisgevingssjabloon te maken voor elk communicatie compliancebeleid.

U kunt er ook voor kiezen om anonimisatie in te stellen voor weergegeven gebruikersnamen bij het onderzoeken van beleidswedstrijden en het ondernemen van actie op berichten.

1. Meld u [https://compliance.microsoft.com](https://compliance.microsoft.com) aan bij het gebruik van referenties voor een beheerdersaccount in uw Microsoft 365 organisatie.

2. Ga in Microsoft 365 compliancecentrum naar **Communicatie compliance.**

3. Als u anonimisatie voor gebruikersnamen wilt configureren, selecteert u het **tabblad Privacy.**

4. Als u anonimisatie wilt inschakelen, selecteert u **Anonieme versies van gebruikersnamen tonen.**

5. Kies **Opslaan**.

6. Ga naar het **tabblad Kennisgevingssjablonen** en selecteer **vervolgens Aankondigingssjabloon maken.**

7. Vul op **de pagina Een kennisgevingssjabloon** wijzigen de volgende velden in:

    - Sjabloonnaam (vereist)
    - Verzenden vanaf (vereist)
    - CC en BCC (optioneel)
    - Onderwerp (vereist)
    - Bericht (vereist)

8. Selecteer **Opslaan om** de kennisgevingssjabloon te maken en op te slaan.

## <a name="step-7-optional-test-your-communication-compliance-policy"></a>Stap 7 (optioneel): Test uw communicatie-compliancebeleid

Nadat u een communicatie-compliancebeleid hebt gemaakt, is het een goed idee om het te testen om ervoor te zorgen dat de voorwaarden die u hebt gedefinieerd, correct worden afgedwongen door het beleid. Mogelijk wilt u ook uw [DLP-beleid (Data Loss Prevention)](create-test-tune-dlp-policy.md) testen als uw beleid voor communicatie compliance gevoelige informatietypen bevat. Zorg ervoor dat u uw beleid de tijd geeft om te activeren, zodat de communicatie die u wilt testen, wordt vastgelegd.

Volg de volgende stappen om uw communicatie-compliancebeleid te testen:

1. Open een e-mailclient, Microsoft Teams of Yammer terwijl u bent aangemeld als een gecontroleerde gebruiker die is gedefinieerd in het beleid dat u wilt testen.

2. Verzend een e-mail, Microsoft Teams chat of Yammer bericht dat voldoet aan de criteria die u hebt gedefinieerd in het communicatie compliancebeleid. Deze test kan een trefwoord, bijlagegrootte, domein, enzovoort zijn. Zorg ervoor dat u bepaalt of de geconfigureerde voorwaardelijke instellingen in het beleid te beperkend of te soepel zijn.

    > [!NOTE]
    > Het kan tot 24 uur duren voordat e-mailberichten volledig worden verwerkt in een beleid. Communicatie in Microsoft Teams, Yammer en platforms van derden kan maximaal 48 uur duren voordat een beleid volledig wordt verwerkt.

3. Meld u aan bij Microsoft 365 revisor die is aangewezen in het communicatie compliancebeleid. Ga naar **Communicatie**  >  **compliancewaarschuwingen om** de waarschuwingen voor uw beleid weer te geven.

4. Herstel de waarschuwing met de herstelbesturingselementen en controleer of de waarschuwing juist is opgelost.

## <a name="next-steps"></a>Volgende stappen

Nadat u deze stappen hebt uitgevoerd om uw eerste communicatiebeleid voor naleving te maken, ontvangt u na 24-48 uur waarschuwingen van activiteitsindicatoren. Configureer zo nodig extra beleid met behulp van de richtlijnen in stap 5 van dit artikel.

Zie Waarschuwingen voor communicatie compliance onderzoeken en corrigeren voor meer informatie over het onderzoeken van waarschuwingen voor communicatie [compliance.](communication-compliance-investigate-remediate.md)
