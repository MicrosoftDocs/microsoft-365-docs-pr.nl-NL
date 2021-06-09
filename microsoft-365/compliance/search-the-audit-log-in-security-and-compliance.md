---
title: Zoek in het auditlogboek in het Beveiligings- en compliancecentrum
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: 'Ga naar het Microsoft 365-compliancecentrum om het geïntegreerde auditlogboek te zoeken zodat u activiteiten van gebruikers en beheerders kunt bekijken in uw organisatie. '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8817ed09673ec23d0a41d680942276bcb1fe297d
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809141"
---
# <a name="search-the-audit-log-in-the-compliance-center"></a>Zoek in het auditlogboek in het compliancecentrum

Wilt u weten of een gebruiker een bepaald document heeft bekeken of een item uit zijn of haar postvak heeft verwijderd? Als dit het geval is, kunt u het Microsoft 365-compliancecentrum gebruiken om in het uniforme controlelogboek te zoeken om gebruikers- en beheerdersactiviteiten in uw organisatie te bekijken. Wat is het doel van een geïntegreerd auditlogboek? Omdat u in Microsoft 365 kunt zoeken naar de volgende soorten [gebruikers- en beheerdersactiviteiten](#audited-activities):

- Gebruikersactiviteit in SharePoint Online en OneDrive voor Bedrijven

- Activiteit van gebruikers in Exchange Online (controlelogboekregistratie voor Exchange-postvakken)

- Beheeractiviteiten in SharePoint Online

- Beheeractiviteiten in Azure Active Directory (de adreslijstservice voor Microsoft 365)

- Beheeractiviteiten in ExchOnline (controlelogboekregistratie voor Exchange-beheerders)

- eDiscovery-activiteiten in het beveiligings- en compliancecentrum

- Activiteiten van gebruikers en beheerders in Power BI

- Activiteit van gebruikers en beheerders in Microsoft Teams

- Activiteit van gebruikers en beheerders in Dynamics 365

- Activiteit van gebruikers en beheerders in Yammer

- Activiteiten van gebruikers en beheerders in Microsoft Power Automate

- Activiteit van gebruikers en beheerders in Microsoft Stream

- Activiteiten van analisten en beheerders in Microsoft Workplace Analytics

- Activiteiten van gebruikers en beheerders in Microsoft Power Apps

- Activiteit van gebruikers en beheerders in Microsoft Forms

- Activiteit van gebruikers en beheerders voor gevoeligheidslabels voor sites die gebruikmaken van SharePoint Online of Microsoft Teams

- Beheerdersactiviteit in Briefing-e-mail en MyAnalytics

## <a name="requirements-to-search-the-audit-log"></a>Vereisten voor het doorzoeken van het auditlogboek

Lees de volgende items voordat u gaat zoeken in het auditlogboek.

- Zoeken in auditlogboek is standaard ingeschakeld voor organisaties met Microsoft 365 en Office 365 Enterprise. Dit geldt ook voor organisaties met een E3/G3- of E5/G5-abonnement. Als u wilt controleren of zoeken in auditlogboek is ingeschakeld, kunt u de volgende opdracht uitvoeren in Exchange Online PowerShell:

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```
  De waarde van `True` voor de eigenschap *UnifiedAuditLogIngestionEnabled* geeft aan dat zoeken in auditlogboek is ingeschakeld. Voor meer informatie, zie [Zoeken in auditlogboeken in- of uitschakelen](turn-audit-log-search-on-or-off.md).

- Als u auditlogboeken wilt doorzoeken, moet aan u de rol Auditlogboeken alleen-weergeven of Auditlogboeken in Exchange Online zijn toegewezen. Deze rollen worden standaard toegewezen aan de rollengroepen Compliancebeheer en Organisatiebeheer op de pagina **Machtigingen** in het Exchange-beheercentrum. Globale beheerders in Office 365 en Microsoft 365 worden automatisch toegevoegd als leden van de rollengroep Organisatiebeheer in Exchange Online. Als u de gebruiker het auditlogboek wilt laten doorzoeken met minimale rechten, kunt u in Exchange Online een aangepaste rollengroep maken, de rol Auditlogboeken alleen-weergeven of Auditlogboeken toevoegen en vervolgens de gebruiker toevoegen als lid van de nieuwe rollengroep. Zie voor meer informatie [Rollengroepen beheren in Exchange Online](/Exchange/permissions-exo/role-groups).

  > [!IMPORTANT]
  > Als u gebruikers de rol Auditlogboeken alleen-weergeven of Auditlogboeken toewijst op de pagina **Machtigingen** in het Beveiligings- en compliancecentrum, dan kunnen ze het auditlogboek niet doorzoeken. U moet deze machtigingen toewijzen in Exchange Online. Dat komt omdat de onderliggende cmdlet voor het doorzoeken van het auditlogboek een Exchange Online-cmdlet is.

- Wanneer een gecontroleerde activiteit wordt uitgevoerd door een gebruiker of beheerder, wordt een auditrecord gegenereerd en opgeslagen in het auditlogboek voor uw organisatie. De tijdsduur dat een auditrecord wordt bewaard (en doorzoekbaar is in het auditlogboek) is afhankelijk van uw Office 365- of Microsoft 365 Enterprise-abonnement, en specifiek het type licentie dat aan specifieke gebruikers is toegewezen.

  - Voor gebruikers waaraan een Office 365 E5- of Microsoft 365 E5-licentie is toegewezen (of gebruikers met een Microsoft 365 E5 Compliance- of Microsoft 365 E5 eDiscovery en Audit invoeglicentie), worden auditrecords voor Azure Active Directory-, Exchange- en SharePoint-activiteit standaard bewaard voor één jaar. Organisaties kunnen ook een bewaarbeleid voor auditlogboeken opstellen om auditrecords voor activiteiten in andere services maximaal een jaar te bewaren. Zie voor meer informatie [Bewaarbeleid voor auditlogboeken beheren](audit-log-retention-policies.md).

    > [!NOTE]
    > Als uw organisatie heeft deelgenomen aan het private preview-programma voor het één jaar bewaren van auditrecords, wordt de bewaartermijn voor auditrecords die zijn gegenereerd vóór de implementatiedatum voor algemene beschikbaarheid niet opnieuw ingesteld.

  - Voor gebruikers waaraan een andere (niet-E5) Office 365- of Microsoft 365-licentie is toegewezen, worden auditrecords 90 dagen bewaard. Zie [de servicebeschrijving van het beveiligings- en compliancecentrum](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) voor een lijst met Office 365- en Microsoft 365-abonnementen die uniforme auditregistratie ondersteunen.

    > [!NOTE]
    > Zelfs wanneer postvakcontrole standaard is ingeschakeld, merkt u mogelijk dat postvakcontrolegebeurtenissen voor sommige gebruikers niet worden gevonden in auditlogboeken in het Beveiligings- en compliancecentrum of via de Office 365 Management Activity-API. Zie ook [Meer informatie over controlelogboekregistratie van postvakken](enable-mailbox-auditing.md#more-information).

- Als u het zoeken in auditlogboeken wilt uitschakelen voor uw organisatie, kunt u de volgende opdracht uitvoeren in een externe PowerShell-sessie met uw Exchange Online-organisatie:

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    Als u het zoeken in auditlogboeken opnieuw wilt inschakelen, kunt u de volgende opdracht uitvoeren in Exchange Online PowerShell:

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

  Zie [Zoeken in auditlogboeken uitschakelen](turn-audit-log-search-on-or-off.md) voor meer informatie.

- Zoals eerder is gezegd, is de onderliggende cmdlet die wordt gebruikt voor het doorzoeken van het auditlogboek een Exchange Online-cmdlet; dit is **Search-UnifiedAuditLog**. Dat betekent dat u deze cmdlet kunt gebruiken om het auditlogboek te doorzoeken in plaats van de pagina **Zoeken in auditlogboeken** in het Beveiligings- en compliancecentrum. U moet deze cmdlet uitvoeren in een externe PowerShell die is verbonden met uw Exchange Online-organisatie. Zie [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) voor meer informatie.

  Voor informatie over het exporteren van de zoekresultaten die zijn geretourneerd door de **Search-UnifiedAuditLog**-cmdlet naar een CSV-bestand, zie de sectie 'Tips voor het exporteren en bekijken van het auditlogboek' in [Auditlogboekrecords exporteren, configureren en weergeven](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log).

- Als u via programmacode gegevens uit het auditlogboek wilt downloaden, raden we aan de Office 365 Management Activity-API te gebruiken in plaats van een PowerShell-script. De Office 365 Management Activity-API is een REST-webservice waarvan u gebruik kunt maken om voor uw organisatie oplossingen te ontwikkelen voor activiteiten, beveiliging en nalevingscontrole. Zie [Office 365 Management Activity-API-referentie](/office/office-365-management-api/office-365-management-activity-api-reference) voor meer informatie.

- Het kan 30 minuten tot 24 uur duren nadat een gebeurtenis heeft plaatsgevonden voordat het bijbehorende auditlogboekrecord wordt geretourneerd in de resultaten van een zoekopdracht in het auditlogboek. De volgende tabel toont de tijd die nodig is voor de verschillende services in Office 365.

  |Microsoft 365-service of -functie|30 minuten|24 uur|
  |:-----|:-----:|:-----:|
  |Defender voor Office 365 en Bedreigingsinformatie|![Vinkje](../media/checkmark.png)||
  |Azure Active Directory (gebruikersaanmeldingsgebeurtenissen)||![Vinkje](../media/checkmark.png)|
  |Azure Active Directory (beheergebeurtenissen)||![Vinkje](../media/checkmark.png)|
  |Preventie van gegevensverlies|![Vinkje](../media/checkmark.png)||
  |Dynamics 365 CRM||![Vinkje](../media/checkmark.png)|
  |eDiscovery|![Vinkje](../media/checkmark.png)||
  |Exchange Online|![Vinkje](../media/checkmark.png)||
  |Microsoft Power Automate||![Vinkje](../media/checkmark.png)|
  |Microsoft Project|![Vinkje](../media/checkmark.png)||
  |Microsoft Stream|![Vinkje](../media/checkmark.png)||
  |Microsoft Teams|![Vinkje](../media/checkmark.png)||
  |Power Apps||![Vinkje](../media/checkmark.png)|
  |Power BI|![Vinkje](../media/checkmark.png)||
  |Beveiligings- en compliancecentrum|![Vinkje](../media/checkmark.png)||
  |Vertrouwelijkheidslabels||![Vinkje](../media/checkmark.png)|
  |SharePoint Online en OneDrive voor Bedrijven|![Vinkje](../media/checkmark.png)||
  |Workplace Analytics|![Vinkje](../media/checkmark.png)||
  |Yammer||![Vinkje](../media/checkmark.png)||
  |Microsoft Forms|![Vinkje](../media/checkmark.png)|
  ||||

- Azure Active Directory (Azure AD) is de directoryservice die wordt gebruikt voor Office 365. Het geïntegreerde auditlogboek bevat activiteiten van gebruikers, groepen, toepassingen, domeinen en adreslijsten die in het Microsoft 365-beheercentrum of in de Azure-beheerportal zijn uitgevoerd. Zie [Azure Active Directory-auditrapportgebeurtenissen](/azure/active-directory/reports-monitoring/concept-audit-logs) voor een volledige lijst met Azure AD-gebeurtenissen.

- Auditlogboekregistratie voor Power BI is niet standaard ingeschakeld. Om naar Power BI-activiteiten te zoeken in het auditlogboek, moet u de controlefunctie in het beheerportal van Power BI inschakelen. Zie de sectie Auditlogboeken in [Power BI-beheerportal](/power-bi/service-admin-portal#audit-logs).

## <a name="search-the-audit-log"></a>Zoeken in het auditlogboek

Hier is het proces voor het zoeken in het auditlogboek in Office 365.

[Stap 1: Een zoekopdracht in het auditlogboek uitvoeren](#step-1-run-an-audit-log-search)

[Stap 2: De zoekresultaten bekijken](#step-2-view-the-search-results)

[Stap 3: De zoekresultaten filteren](#step-3-filter-the-search-results)

[Stap 4: De zoekresultaten naar een bestand exporteren](#step-4-export-the-search-results-to-a-file)

### <a name="step-1-run-an-audit-log-search"></a>Stap 1: Een zoekopdracht in het auditlogboek uitvoeren

1. Ga naar [https://protection.office.com](https://protection.office.com).

    > [!TIP]
    > Gebruik een persoonlijke browsersessie (geen normale sessie) om het Beveiligings- en compliancecentrum te openen. Hierdoor wordt voorkomen dat de referenties waarmee u bent aangemeld, worden gebruikt. Om een InPrivate-browsing-sessie in Internet Explorer of Microsoft Edge te openen, drukt u op CTRL+SHIFT+P. Druk op CTRL+SHIFT+N om een privé-browsersessie te openen in Google Chrome (ook wel een incognitovenster genoemd).

2. Meld u aan met uw werk- of schoolaccount.

3. Klik in het linkerdeelvenster van het Beveiligings- en compliancecentrum op **Zoekacties en onderzoek** en vervolgens op **Zoeken in het auditlogboek**.

    De pagina **Zoeken in het auditlogboek** wordt weergegeven.

    ![Configureer criteria en klik vervolgens op Zoeken om een rapport uit te voeren](../media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)

    > [!NOTE]
    > U moet eerst controlelogboekregistratie inschakelen voordat u een zoekopdracht in het auditlogboek kunt uitvoeren. Als de koppeling **Registreren van gebruikers- en beheerdersactiviteit starten** wordt weergegeven, klikt u erop om de controle in te schakelen. Als u deze koppeling niet ziet, is controle al ingeschakeld voor uw organisatie.

4. Configureer de volgende zoekcriteria: 

   1. **Activiteiten**: klik op de vervolgkeuzelijst om activiteiten weer te geven die u kunt zoeken. Activiteiten van gebruikers en beheerders staan gerangschikt in groepen met gerelateerde activiteiten. U kunt specifieke activiteiten selecteren of u kunt op de naam van de activiteitengroep klikken om alle activiteiten in de groep te selecteren. U kunt ook op een geselecteerde activiteit klikken om de selectie te wissen. Als u de zoekopdracht hebt uitgevoerd, worden alleen de vermeldingen in het auditlogboek voor de geselecteerde activiteiten weergegeven. Als u **Resultaten tonen voor alle activiteiten** selecteert, worden de resultaten weergegeven voor alle activiteiten die zijn uitgevoerd door de geselecteerde gebruiker of groep gebruikers.

      Er worden meer dan honderd activiteiten van gebruikers en beheerders in het auditlogboek vastgelegd. Klik op het tabblad **Gecontroleerde activiteiten** bij het onderwerp van dit artikel om de beschrijvingen van elke activiteit in elk van de verschillende services te zien.

   1. **Begindatum** en **Einddatum**: standaard worden de laatste zeven dagen geselecteerd. Selecteer een bereik voor de datum en tijd om de gebeurtenissen weer te geven die in die periode hebben plaatsgevonden.  De datum en tijd worden op lokale tijd weergegeven. Het grootste datumbereik dat u kunt opgeven is 90 dagen. Er wordt een fout weergegeven als het geselecteerde datumbereik groter is dan 90 dagen.

      > [!TIP]
      > Als u het maximum datumbereik van 90 dagen gebruikt, selecteert u het huidige tijdstip voor **Begindatum**. Anders krijgt u de foutmelding dat de begindatum eerder is dan de einddatum. Als u de controle de afgelopen 90 dagen hebt ingeschakeld, kan het maximum datumbereik niet beginnen vóór de datum waarop de controle is ingeschakeld.

   1. **Gebruikers**: klik in dit vak en selecteer een of meer gebruikers waarvoor u de zoekresultaten wilt weergeven. De vermeldingen in het auditlogboek voor de geselecteerde activiteit die is uitgevoerd door de gebruikers die u in dit vak selecteert, worden in de lijst met resultaten weergegeven. Laat dit vak leeg als u vermeldingen wilt zien voor alle gebruikers (en serviceaccounts) in uw organisatie.

   1. **Bestand, map of site**: typ de naam (of een gedeelte ervan) van het bestand of de map om te zoeken naar activiteit met betrekking tot dat bestand of die map die het opgegeven trefwoord bevat. U kunt ook een URL van een bestand of map opgeven. Als u een URL gebruikt, zorg er dan voor dat u het volledige URL-pad typt of als u een deel van de URL typt, geen speciale tekens of spaties opneemt.

      Laat dit vak leeg als u vermeldingen wilt zien voor alle bestanden en mappen in uw organisatie.

      > [!TIP]
      >
      > - Als u op zoek bent naar alle activiteiten die zijn gerelateerd aan een **site**, voegt u het jokerteken (\*) toe na de URL om alle vermeldingen voor die site te retourneren; bijvoorbeeld, `"https://contoso-my.sharepoint.com/personal*"`.
      >
      > - Als u op zoek bent naar alle activiteiten die zijn gerelateerd aan een **bestand**, voegt u het jokerteken (\*) toe voor de bestandsnaam om alle vermeldingen voor dat bestand te retourneren; bijvoorbeeld, `"*Customer_Profitability_Sample.csv"`.

5. Klik op **Zoeken** om de zoekopdracht met uw zoekcriteria uit te voeren. 

   De zoekresultaten worden geladen en worden na enkele ogenblikken onder **Resultaten** weergegeven. Als de zoekopdracht is voltooid, wordt het aantal gevonden resultaten weergegeven. Er worden maximaal 5000 gebeurtenissen weergegeven in het deelvenster **Resultaten** in stappen van 150 gebeurtenissen. Als er meer dan 5000 gebeurtenissen voldoen aan de zoekcriteria, worden de meest recente 5000 gebeurtenissen weergegeven.

   ![Het aantal resultaten wordt weergegeven nadat de zoekactie is voltooid](../media/986216f1-ca2f-4747-9480-e232b5bf094c.png)

#### <a name="tips-for-searching-the-audit-log"></a>Tips voor het zoeken in het auditlogboek

- U kunt specifieke activiteiten opgeven om op te zoeken door op de namen van de activiteiten te klikken. U kunt ook op alle activiteiten in een groep zoeken (bijvoorbeeld **Activiteiten in verband met bestanden en mappen**) door op de groepsnaam te klikken. Als er een activiteit is geselecteerd, kunt u erop klikken als u de selectie wilt wissen. U kunt ook het zoekvak gebruiken om de activiteiten weer te geven die het trefwoord bevatten dat u typt.

  ![Klik op de groepsnaam van de activiteit om alle activiteiten te selecteren](../media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)

- Selecteer **Resultaten tonen voor alle activiteiten** in de lijst **Activiteiten** om vermeldingen uit het auditlogboek van de Exchange-beheerder weer te geven. Gebeurtenissen uit dit auditlogboek geven een cmdlet-naam weer (bijvoorbeeld **Set-Mailbox**) in de kolom **Activiteit** van de resultaten. Klik voor meer informatie op het tabblad **Gecontroleerde activiteiten** in dit onderwerp en klik vervolgens op **Exchange-beheeractiviteiten**.

  Op dezelfde manier zijn er enkele controleactiviteiten waarvoor geen overeenkomstig item in de **Activiteitenlijst** staat. Als u de naam van de bewerking voor deze activiteiten weet, kunt u zoeken naar alle activiteiten, vervolgens de resultaten filteren door de naam van de bewerking in te typen in het vak voor de kolom **Activiteit**. Zie [Stap 3: de zoekresultaten filteren](#step-3-filter-the-search-results) voor meer informatie over het filteren van resultaten.

- Klik op **Wissen** om de huidige zoekcriteria te wissen. Het datumbereik wordt weer terug ingesteld op de standaardwaarde van de afgelopen zeven dagen. U kunt ook op **Alles wissen om resultaten te tonen voor alle activiteiten** klikken om alle geselecteerde activiteiten te annuleren.

- Als er 5000 resultaten worden gevonden, kunt u aannemen dat er meer dan 5000 gebeurtenissen zijn die aan de zoekcriteria voldoen. U kunt de zoekcriteria verfijnen en de zoekopdracht herhalen zodat er minder resultaten worden weergegeven, maar u kunt ook alle zoekresultaten exporteren via **Resultaten exporteren** \> **Alle resultaten downloaden**.

### <a name="step-2-view-the-search-results"></a>Stap 2: de zoekresultaten bekijken

De resultaten van een zoekopdracht in een auditlogboek worden weergegeven onder **Resultaten** op de pagina **Zoeken in het auditlogboek**. Zoals eerder vermeld, worden maximaal 5,000 (nieuwste) gebeurtenissen in pagina's van 150 gebeurtenissen weergegeven. Om meer gebeurtenissen weer te geven, kunt u de schuifbalk in het deelvenster **Resultaten** gebruiken of u kunt op **Shift + End** drukken om de volgende 150 gebeurtenissen weer te geven.

De resultaten bevatten de volgende informatie over alle gebeurtenissen die door de zoekopdracht worden geretourneerd:

- **Datum**: de datum en tijd (in de lokale tijd) waarop de gebeurtenis heeft plaatsgevonden.

- **IP-adres**: het IP-adres van het apparaat dat is gebruikt toen de activiteit in het logboek werd vastgelegd. Het IP-adres wordt weergegeven in een IPv4- of IPv6-adresindeling.

   > [!NOTE]
  > Voor sommige services is de waarde die in dit veld wordt weergegeven mogelijk het IP-adres van een vertrouwde applicatie (bijvoorbeeld Office op the web-apps) die namens een gebruiker de service aanroept en niet het IP-adres van het apparaat dat is gebruikt door een persoon die de activiteit heeft uitgevoerd. Voor beheeractiviteiten (of activiteiten die door een systeemaccount worden uitgevoerd) voor Azure Active Directory-gerelateerde gebeurtenissen wordt het IP-adres ook niet geregistreerd en is de waarde die in dit veld wordt weergegeven, `null`.

- **Gebruiker**: de gebruiker (of serviceaccount) die de actie heeft uitgevoerd die de gebeurtenis heeft veroorzaakt.

- **Activiteit**: de activiteit die door de gebruiker is uitgevoerd. Deze waarde komt overeen met de activiteiten die u hebt geselecteerd in de vervolgkeuzelijst **Activiteiten**. Voor een gebeurtenis uit het auditlogboek voor Exchange-beheerders is de waarde in deze kolom een Exchange-cmdlet.

- **Item**: het object dat is gemaakt of gewijzigd als gevolg van de bijbehorende activiteit. Bijvoorbeeld het bestand dat is bekeken of gewijzigd of het gebruikersaccount dat is bijgewerkt. Niet alle activiteiten hebben een waarde in deze kolom.

- **Detailgegevens**: aanvullende informatie over een activiteit. Nogmaals, niet alle activiteiten hebben een waarde.

> [!TIP]
> Klik op een kolomkop onder **Resultaten** om de resultaten te sorteren. U kunt de resultaten sorteren van A tot Z of van Z tot A. Klik op de kop **Datum** om de resultaten van oudste naar nieuwste of van nieuwste naar oudste te sorteren.

#### <a name="view-the-details-for-a-specific-event"></a>De details van een bepaalde gebeurtenis weergeven

U kunt meer details over een gebeurtenis bekijken als u op de gebeurtenisrecord klikt in de lijst met zoekresultaten. De pagina **Details** verschijnt met daarop de gedetailleerde eigenschappen uit de gebeurtenisrecord. De eigenschappen die worden weergegeven, zijn afhankelijk van de service waarin de gebeurtenis plaatsvindt. Als u deze details wilt weergeven, klikt u op **Meer informatie**. Zie voor beschrijvingen [Gedetailleerde eigenschappen in de auditlogboek](detailed-properties-in-the-office-365-audit-log.md).

![Klik op Meer informatie om de gedetailleerde eigenschappen van de gebeurtenisrecord in het auditlogboek weer te geven.](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

### <a name="step-3-filter-the-search-results"></a>Stap 3: de zoekresultaten filteren

Behalve sorteren kunt u de resultaten van een zoekopdracht in het auditlogboek ook filteren. Dit is een geweldige functie waarmee u snel de resultaten kunt filteren op een specifieke gebruiker of activiteit. In eerste instantie kunt u in brede zin zoeken en vervolgens de resultaten filteren op bepaalde gebeurtenissen. Vervolgens kunt u de zoekcriteria verfijnen en de zoekopdracht opnieuw uitvoeren voor een meer beknopte verzameling resultaten.

U filtert de resultaten als volgt:

1. Voer een zoekopdracht in het auditlogboek uit.

2. Klik op **Resultaten filteren** wanneer de resultaten worden weergegeven.

   Onder elke kolomkop wordt een vak met trefwoorden weergegeven.

3. Klik op een van de vakken onder een kolomkop en typ een woord of zinsdeel, afhankelijk van de kolom die u filtert. De resultaten worden dynamisch aangepast en de gebeurtenissen die met het filter overeenkomen, worden weergegeven.

   ![Typ een woord in het filter om gebeurtenissen weer te geven die overeenkomen met het filter](../media/542dc323-a997-402c-934b-cc5e218e50bc.png)

4. Als u een filter wilt wissen, klikt u op de **X** in het filtervak of op **Filter verbergen**.

> [!TIP]
> Als u gebeurtenissen uit het auditlogboek voor Exchange-beheerders wilt weergeven, typt u een **-** (streepje) in het filtervak **Activiteit**. Hierdoor worden de namen van de cmdlets weergegeven in de kolom **Activiteit** voor gebeurtenissen van Exchange-beheerders. U kunt vervolgens de namen van de cmdlets op alfabetische volgorde sorteren.

### <a name="step-4-export-the-search-results-to-a-file"></a>Stap 4: de zoekresultaten naar een bestand exporteren

U kunt de resultaten van een zoekopdracht in een auditlogboek exporteren naar een door komma's gescheiden bestand (CSV) op uw lokale computer. U kunt dit bestand in Microsoft Excel openen en functies gebruiken als zoeken, sorteren, filteren en één kolom (die meerdere eigenschappen bevat) splitsen in meerdere kolommen.

1. Voer een zoekopdracht in een auditlogboek uit en pas de zoekcriteria aan tot u de gewenste resultaten hebt.

2. Klik op **Resultaten exporteren** en selecteer een van de volgende opties:

   - **Geladen resultaten opslaan**: kies deze optie als u alleen de vermeldingen wilt exporteren die op de pagina **Zoeken in auditlogboek** onder **Resultaten** worden weergegeven.  Het CSV-bestand dat wordt gedownload bevat dezelfde kolommen (en gegevens) die worden weergegeven op de pagina (Datum, Gebruiker, Activiteit, Item en Details). Er wordt een extra kolom (**Meer**) opgenomen in het CSV-bestand met meer informatie afkomstig van de vermelding in het auditlogboek. Omdat u dezelfde resultaten exporteert die zijn geladen (en kunnen worden weergegeven) op de pagina **Zoeken in auditlogboek**, worden er maximaal 5000 vermeldingen geëxporteerd.

   - **Alle resultaten downloaden**: kies deze optie voor het exporteren van alle vermeldingen in het auditlogboek die voldoen aan de zoekcriteria. Kies deze optie voor een groot aantal zoekresultaten om alle vermeldingen uit het auditlogboek te downloaden (naast de 5000 auditrecords die op de pagina **Zoeken in auditlogboek** worden weergegeven). Met deze optie worden alle onbewerkte gegevens uit het auditlogboek gedownload in een CSV-bestand. De gedownloade resultaten bevatten tevens aanvullende gegevens uit het auditlogboek in de kolom **AuditData**. Het downloaden van het bestand kan langer duren als u deze exportoptie kiest, omdat het bestand veel groter kan zijn dan het bestand dat wordt gedownload als u de andere optie kiest.

     > [!IMPORTANT]
     > U kunt maximaal 50.000 vermeldingen (als gevolg van één zoekopdracht) in een CSV-bestand downloaden. Als er 50.000 resultaten in het CSV-bestand zijn gedownload, kunt u aannemen dat er meer dan 50.000 gebeurtenissen zijn die aan de zoekcriteria voldoen. Als u meer wilt exporteren, kunt u een datumbereik kiezen om het aantal vermeldingen in het auditlogboek te verminderen. Mogelijk moet u meerdere zoekopdrachten uitvoeren met kleinere datumbereiken als u meer dan 50.000 vermeldingen wilt exporteren.

3. Als u een exportoptie hebt geselecteerd, wordt onder aan het venster een bericht weergegeven waarin u wordt gevraagd het CSV-bestand te openen en het op te slaan in de map Downloads of een andere, speciale map.

#### <a name="more-information-about-exporting-and-viewing-audit-log-search-results"></a>Meer informatie over het exporteren en weergeven van zoekresultaten vanuit het auditlogboek

- Als u alle zoekresultaten downloadt, bevat het CSV-bestand de kolom **AuditData**, met aanvullende informatie over elke gebeurtenis. De gegevens in deze kolom bestaan uit een JSON-object dat meerdere eigenschappen uit de auditlogboekrecord bevat. Elke *eigenschap:waarde*-paar in het JSON-object wordt gescheiden door een komma. U kunt het transformatiehulpmiddel JSON in Power Query Editor in Excel gebruiken om de **AuditData**-kolom te splitsen in meerdere kolommen, zodat elke eigenschap in het JSON-object een eigen kolom heeft. Hiermee kunt u sorteren en filteren op een of meer van deze eigenschappen. Zie [Auditlogboekrecords exporteren, configureren en weergeven](export-view-audit-log-records.md) voor stapsgewijze instructies voor de Power Query Editor om het JSON-object te transformeren.

  Na het splitsen van de kolom **AuditData** kunt u filteren op de kolom **Bewerkingen** als u de gedetailleerde eigenschappen voor een bepaald type activiteit wilt weergeven.

- Met de optie **Alle resultaten downloaden** worden de onbewerkte gegevens vanuit het auditlogboek in een CSV-bestand gedownload. Dit bestand bevat andere kolomnamen (CreationDate, UserIds, Operation, AuditData) dan het bestand dat wordt gedownload als u de optie **Geladen resultaten opslaan** selecteert. De waarden in de twee verschillende CSV-bestanden voor dezelfde activiteit kunnen ook verschillen. Bijvoorbeeld: de activiteit in de kolom **Activiteit** in het CSV-bestand kan een andere waarde hebben dan de 'gebruikersvriendelijke' versie die wordt weergegeven in de kolom **Activiteit** op de pagina **Zoeken in auditlogboek**. Bijvoorbeeld: MailboxLogin versus Gebruiker die is aangemeld bij het postvak.

- Als u alle resultaten hebt gedownload van een zoekopdracht die bestaat uit de gebeurtenissen van verschillende services, dan bevat de kolom **AuditData** in het CSV-bestand verschillende eigenschappen, afhankelijk van de service waarmee de actie is uitgevoerd. Vermeldingen uit bijvoorbeeld Exchange- en Microsoft Azure AD-auditlogboeken bevatten de eigenschap **ResultStatus**. Hiermee wordt aangegeven of de actie al dan niet is geslaagd. Deze eigenschap is niet opgenomen voor gebeurtenissen in SharePoint. Op dezelfde manier hebben SharePoint-gebeurtenissen een eigenschap waarmee de site-URL wordt aangegeven voor activiteiten in verband met bestanden en mappen. Als u dit gedrag wilt beperken, kunt u verschillende zoekopdrachten uitvoeren om de resultaten voor activiteiten van één service te exporteren.

  Zie [Gedetailleerde eigenschappen in het auditlogboek](detailed-properties-in-the-office-365-audit-log.md) voor een beschrijving van veel eigenschappen die staan vermeld in de kolom **AuditData** van het CSV-bestand bij het downloaden van alle resultaten, en de service waartoe ze behoren.

## <a name="audited-activities"></a>Gecontroleerde activiteiten

In de tabellen in deze sectie worden de activiteiten beschreven die in Office 365 worden gecontroleerd. U kunt op deze gebeurtenissen zoeken door het auditlogboek in het beveiligings- en compliancecentrum te doorzoeken.

Deze tabellen groeperen verwante activiteiten of de activiteiten uit een specifieke service. De tabellen bevatten de beschrijvende naam die wordt weergegeven in de vervolgkeuzelijst **Activiteiten** en de naam van de overeenkomstige bewerking die wordt weergegeven in de gedetailleerde informatie van een auditrecord en in het CSV-bestand wanneer u de zoekresultaten exporteert. Zie [Gedetailleerde eigenschappen in het auditlogboek](detailed-properties-in-the-office-365-audit-log.md) voor beschrijvingen van de gedetailleerde informatie.

Klik op een van de volgende koppelingen om naar een specifieke tabel te gaan.

:::row:::
    :::column:::
        [Activiteiten voor bestanden en pagina's](#file-and-page-activities)
    :::column-end:::
    :::column:::
        [Mapactiviteiten](#folder-activities)
    :::column-end:::
    :::column:::
        [Activiteiten in de SharePoint-lijst](#sharepoint-list-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Activiteiten voor het delen en aanvragen voor toegang](#sharing-and-access-request-activities)
    :::column-end:::
    :::column:::
        [Synchronisatieactiviteiten](#synchronization-activities)
    :::column-end:::
    :::column:::
        [Activiteiten voor sitemachtigingen](#site-permissions-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Activiteiten voor sitebeheer](#site-administration-activities)
    :::column-end:::
    :::column:::
        [Activiteiten voor Exchange-postvakken](#exchange-mailbox-activities)
    :::column-end:::
    :::column:::
        [Activiteiten voor gebruikersbeheer](#user-administration-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Activiteiten voor groepsbeheer via Azure Active Directory](#azure-ad-group-administration-activities)
    :::column-end:::
    :::column:::
        [Activiteiten voor toepassingsbeheer](#application-administration-activities)
    :::column-end:::
    :::column:::
        [Activiteiten in verband met rolbeheer](#role-administration-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Activiteiten in verband met adreslijstbeheer](#directory-administration-activities)
    :::column-end:::
    :::column:::
        [Activiteiten in eDiscovery](#ediscovery-activities)
    :::column-end:::
    :::column:::
        [Geavanceerde activiteiten in eDiscovery](#advanced-ediscovery-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Activiteiten in Power BI](#power-bi-activities)
    :::column-end:::
    :::column:::
        [Microsoft Workplace Analytics](#workplace-analytics-activities)
    :::column-end:::
    :::column:::
        [Activiteiten in Microsoft Teams](#microsoft-teams-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Activiteiten in Microsoft Teams Gezondheidszorg](#microsoft-teams-healthcare-activities)
    :::column-end:::
    :::column:::
        [Activiteiten in Microsoft Teams Shifts](#microsoft-teams-shifts-activities)
    :::column-end:::
    :::column:::
        [Activiteiten in Yammer](#yammer-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Activiteiten in Microsoft Power Automate](#microsoft-power-automate-activities)
    :::column-end:::
    :::column:::
        [Activiteiten in Microsoft Power Apps](#microsoft-power-apps-activities)
    :::column-end:::
    :::column:::
        [Activiteiten in Microsoft Stream](#microsoft-stream-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Activiteiten in Inhoudsverkenner](#content-explorer-activities)
    :::column-end:::
    :::column:::
        [Activiteiten in quarantaine](#quarantine-activities)
    :::column-end:::
    :::column:::
        [Activiteiten in Microsoft Forms](#microsoft-forms-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Activiteiten voor gevoeligheidslabels](#sensitivity-label-activities)
    :::column-end:::
    :::column:::
        [Activiteiten met bewaarbeleid en bewaarlabels](#retention-policy-and-retention-label-activities)
    :::column-end:::
    :::column:::
        [Activiteiten voor informatie-e-mailberichten](#briefing-email-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Activiteiten in MyAnalytics](#myanalytics-activities)
    :::column-end:::
    :::column:::
        [Informatiebelemmeringen in Teams](#information-barriers-activities)
    :::column-end:::
    :::column:::
        [Activiteiten van Exchange-beheerder](#exchange-admin-audit-log)
    :::column-end:::
:::row-end:::

### <a name="file-and-page-activities"></a>Activiteiten van bestanden en pagina's

In de volgende tabel worden de activiteiten in bestanden en pagina's in SharePoint Online en OneDrive voor Bedrijven beschreven.

|Beschrijvende naam|Bewerking|Beschrijving|
|:-----|:-----|:-----|
|Bestand geopend|FileAccessed|Gebruiker of systeemaccount opent een bestand.|
|(geen)|FileAccessedExtended|Dit is gerelateerd aan de activiteit "Geopend bestand" (FileAccessed). Een FileAccessedExtended-gebeurtenis wordt geregistreerd wanneer dezelfde persoon gedurende een langere periode (tot 3 uur) voortdurend een bestand opent. <br/><br/> Het doel van het registreren van FileAccessedExtended-gebeurtenissen is het aantal FileAccessed-gebeurtenissen te reduceren dat wordt geregistreerd wanneer een bestand voortdurend wordt geopend. Zo wordt u minder belast door meerdere FileAccessed-records voor wat in feite dezelfde gebruikersactiviteit is, en kunt u zich concentreren op de eerste (en belangrijkere) FileAccessed-gebeurtenis.|
|Bewaarlabel voor een bestand gewijzigd|ComplianceSettingChanged|Er is een bewaarlabel toegepast op of verwijderd uit een document. Deze gebeurtenis wordt geactiveerd wanneer een bewaarlabel handmatig of automatisch wordt toegepast op een bericht.|
|Recordstatus gewijzigd in vergrendeld|LockRecord|De recordstatus van een bewaarlabel waarin een document wordt aangeduid als een record, is vergrendeld. Dit betekent dat het document niet kan worden gewijzigd of verwijderd. Alleen gebruikers die ten minste de inzendermachtiging voor een site hebben toegewezen, kunnen de recordstatus van een document wijzigen.|
|Recordstatus gewijzigd in ontgrendeld|UnlockRecord|De recordstatus van een bewaarlabel waarin een document wordt aangeduid als een record, is ontgrendeld. Dit betekent dat het document kan worden gewijzigd of verwijderd. Alleen gebruikers die ten minste de inzendermachtiging voor een site hebben toegewezen, kunnen de recordstatus van een document wijzigen.|
|Bestand ingecheckt|FileCheckedIn|Gebruiker checkt een document in dat vanuit een documentbibliotheek is uitgecheckt.|
|Bestand uitgecheckt|FileCheckedOut|Gebruiker checkt een document uit dat zich in een documentbibliotheek bevindt. Gebruikers kunnen documenten die met hen zijn gedeeld uitchecken en er wijzigingen in aanbrengen.|
|Bestand gekopieerd|FileCopied|Gebruiker kopieert een bestand vanaf een site. Het gekopieerde bestand kan worden opgeslagen in een andere map op de site.|
|Bestand verwijderd|FileDeleted|Gebruiker verwijdert een bestand van een site.|
|Bestand verwijderd uit de prullenbak|FileDeletedFirstStageRecycleBin|Gebruiker verwijdert een bestand uit de prullenbak van een site.|
|Bestand verwijderd uit een prullenbak tweede stadium|FileDeletedSecondStageRecycleBin|Gebruiker verwijdert een bestand uit de prullenbak tweede stadium van een site.|
|Verwijderd bestand gemarkeerd als record|RecordDelete|Een document of e-mailbericht dat als record is gemarkeerd, is verwijderd. Een item wordt beschouwd als een record wanneer een bewaarlabel waarin items als een record worden aangeduid, wordt toegepast op inhoud.|
|Gedetecteerde niet-overeenkomende documentgevoeligheid|DocumentSensitivityMismatchDetected|Gebruiker uploadt een document naar een site die is beveiligd met een vertrouwelijkheidslabel en het document heeft een vertrouwelijkheidslabel met een hogere prioriteit dan het vertrouwelijkheidslabel dat op de site is toegepast.<br/><br/> Deze gebeurtenis wordt niet geactiveerd als het document een gevoeligheidslabel met een lagere prioriteit heeft dan het gevoeligheidslabel dat op de site is toegepast. Een document met het label Algemeen wordt bijvoorbeeld geüpload naar een site met het label Vertrouwelijk. Zie voor meer informatie over prioriteit van gevoeligheidslabels [Labelprioriteit (volgorde is van belang)](sensitivity-labels.md#label-priority-order-matters).|
|Schadelijke software vastgesteld in bestand|FileMalwareDetected|Met de anti-virusen engine van SharePoint wordt malware in een bestand gedetecteerd.|
|Uitchecken van bestand genegeerd|FileCheckOutDiscarded|De gebruiker doet een uitgecheckt bestand teniet (of maakt dit ongedaan). Dat betekent dat eventuele aangebrachte wijzigingen bij het uitchecken aan het bestand worden tenietgedaan en niet opgeslagen in de versie van het document in de documentbibliotheek.|
|Bestand gedownload|FileDownloaded|Gebruiker downloadt een document van een site.|
|Bestand gewijzigd|FileModified|Gebruiker of systeemaccount wijzigt de inhoud of de eigenschappen van een document op een site.|
|(geen)|FileModifiedExtended|Dit is gerelateerd aan de activiteit "Gewijzigd bestand" (FileModified).Een FileModifiedExtended-gebeurtenis wordt geregistreerd wanneer dezelfde persoon gedurende een langere periode (tot 3 uur) voortdurend een bestand wijzigt. <br/><br/> Het doel van het registreren van FileModifiedExtended-gebeurtenissen is het aantal FileModified-gebeurtenissen te reduceren dat wordt geregistreerd wanneer een bestand voortdurend wordt gewijzigd. Zo wordt u minder belast door meerdere FileModified-records voor wat in feite dezelfde gebruikersactiviteit is, en kunt u zich concentreren op de eerste (en belangrijkere) FileModified-gebeurtenis.|
|Bestand verplaatst|FileMoved|Gebruiker verplaatst een document vanaf de huidige locatie op een site naar een nieuwe locatie.|
|(geen)|FilePreviewed|Gebruiker bekijkt voorbeelden van bestanden op een SharePoint- of OneDrive voor Bedrijven-site. Deze gebeurtenissen vinden meestal plaats bij grote hoeveelheden op basis van één activiteit, zoals het weergeven van een afbeeldingengalerie.|
|Uitgevoerde zoekquery|SearchQueryPerformed|Gebruiker of systeemaccount voert een zoekopdracht uit in SharePoint of OneDrive voor Bedrijven. Enkele veelvoorkomende scenario's waarin een serviceaccount een zoekopdracht uitvoert, zijn onder meer het toepassen van een eDiscovery-bewaarplicht en bewaarbeleid op sites en OneDrive-accounts, en het automatisch toepassen van bewaar- of vertrouwelijkheidslabels op site-inhoud.|
|Alle secundaire versies van een bestand gerecycled|FileVersionsAllMinorsRecycled|Gebruiker verwijdert alle secundaire versies uit de versiegeschiedenis van een bestand. De verwijderde versies worden verplaatst naar de prullenbak van de site.|
|Alle versies van bestand gerecycled|FileVersionsAllRecycled|Gebruiker verwijdert alle versies uit de versiegeschiedenis van een bestand. De verwijderde versies worden verplaatst naar de prullenbak van de site.|
|Gerecyclede versie van bestand|FileVersionRecycled|Gebruiker verwijdert een versies uit de versiegeschiedenis van een bestand. De verwijderde versie wordt verplaatst naar de prullenbak van de site.|
|Naam van bestand gewijzigd|FileRenamed|Gebruiker wijzigt de naam van een document op een site.|
|Bestand teruggezet|FileRestored|Gebruiker zet een document terug vanuit de Prullenbak van een site. |
|Bestand geüpload|FileUploaded|Gebruiker uploadt een document naar een map op een site. |
|Pagina bekeken|PageViewed|Gebruiker bekijkt een pagina op een site. Het gaat hierbij niet om bestanden die zich in een documentbibliotheek bevinden en via een webbrowser zijn bekeken.|
|(geen)|PageViewedExtended|Dit is gerelateerd aan de activiteit "Bekeken pagina" (PageViewed).Een PageViewedExtended-gebeurtenis wordt geregistreerd wanneer dezelfde persoon gedurende een langere periode (tot 3 uur) voortdurend een webpagina bekijkt. <br/><br/> Het doel van het registreren van PageViewedExtended-gebeurtenissen is het aantal PageViewed-gebeurtenissen te reduceren dat wordt geregistreerd wanneer een pagina voortdurend wordt bekeken. Zo wordt u minder belast door meerdere PageViewed-records voor wat in feite dezelfde gebruikersactiviteit is, en kunt u zich concentreren op de eerste (en belangrijkere) PageViewed-gebeurtenis.|
|Gesignaleerd door klant weergeven|ClientViewSignaled|De client van een gebruiker (zoals een website of mobiele app) geeft aan dat de aangegeven pagina is bekeken door de gebruiker. Deze activiteit wordt vaak geregistreerd na een PagePrefetched-gebeurtenis voor een pagina. <br/><br/>**OPMERKING**: omdat ClientViewSignaled-gebeurtenissen worden gesignaleerd door de client en niet door de server, is het mogelijk dat de gebeurtenis niet wordt geregistreerd door de server en daarom mogelijk niet in het auditlogboek verschijnt. Het is ook mogelijk dat gegevens in de controlerecord niet betrouwbaar zijn. Omdat de identiteit van de gebruiker echter wordt gevalideerd door het token dat wordt gebruikt om het signaal te maken, is de identiteit van de gebruiker in de bijbehorende auditrecord correct. |
|(geen)|PagePrefetched|De client van een gebruiker (zoals een website of mobiele app) heeft de aangegeven pagina opgevraagd om de prestaties te helpen verbeteren als de gebruiker ernaar bladert. Deze gebeurtenis wordt geregistreerd om aan te geven dat de pagina-inhoud is weergegeven aan de client van de gebruiker. Deze gebeurtenis is geen definitieve indicatie dat de gebruiker de pagina heeft bezocht. <br/><br/> Wanneer de pagina-inhoud wordt weergegeven door de client (op verzoek van de gebruiker), moet een ClientViewSignaled-gebeurtenis worden gegenereerd. Niet alle clients ondersteunen het aangeven van vooraf ophalen, en daarom kunnen sommige vooraf opgehaalde activiteiten in plaats daarvan worden geregistreerd als PageViewed-gebeurtenissen.|
||||

#### <a name="frequently-asked-questions-about-fileaccessed-and-filepreviewed-events"></a>Veelgestelde vragen over FileAccessed- en FilePreviewed-gebeurtenissen

**Kunnen niet-gebruikersactiviteiten FilePreviewed-auditrecords activeren die een user-agent zoals 'OneDriveMpc-Transform_Thumbnail' bevatten?**

Wij zijn niet op de hoogte van scenario's waarbij niet-gebruikersacties gebeurtenissen als deze genereren. Gebruikersacties zoals het openen van een gebruikersprofielkaart (door op hun naam of e-mailadres te klikken in een bericht in de webversie van Outlook) zouden soortgelijke gebeurtenissen genereren.

**Worden oproepen naar de OneDriveMpc-Transform_Thumbnail altijd opzettelijk getriggerd door de gebruiker?**

Nee. Maar vergelijkbare gebeurtenissen kunnen worden geregistreerd als gevolg van het vooraf ophalen van de browser.

**Als er een FilePreviewed-gebeurtenis wordt weergegeven die afkomstig is van een ip-adres dat door Microsoft is geregistreerd, betekent dit dan dat de preview is weergegeven op het scherm van het apparaat van de gebruiker?**

Nee. De gebeurtenis is mogelijk geregistreerd als gevolg van vooraf ophalen van de browser.

**Zijn er scenario's waarin een gebruiker die een voorbeeld van een document bekijkt, FileAccessed-gebeurtenissen genereert?**

Zowel de gebeurtenissen FilePreviewed als de FileAccessed geven aan dat de oproep van een gebruiker leidde tot het lezen van het bestand (of het lezen van een miniatuurweergave van het bestand). Hoewel deze gebeurtenissen bedoeld zijn overeen te komen met de bedoeling van preview versus toegang, is het onderscheid tussen gebeurtenissen geen garantie voor de bedoeling van de gebruiker.

#### <a name="the-appsharepoint-user-in-audit-records"></a>De app\@SharePoint-gebruiker in auditrecords

In auditrecords voor sommige bestandsactiviteiten (en andere SharePoint-gerelateerde activiteiten), ziet u mogelijk dat de gebruiker die de activiteit heeft uitgevoerd (geïdentificeerd in de velden User en UserId) app@sharepoint is. Hiermee wordt aangegeven dat de 'gebruiker' die de activiteit heeft uitgevoerd een toepassing is. In dit geval is aan de toepassing in SharePoint toestemming verleend om namens een gebruiker, beheerder of service acties voor de hele organisatie uit te voeren (zoals het doorzoeken van een SharePoint-site of OneDrive-account). Dit proces voor het verlenen van machtigingen aan een toepassing wordt *SharePoint App-Only*-toegang genoemd. Hiermee wordt aangegeven dat de verificatie die aan SharePoint wordt gepresenteerd om een actie uit te voeren, is aangebracht door een toepassing in plaats van door een gebruiker. Daarom wordt de gebruiker app@sharepoint in bepaalde auditrecords geïdentificeerd. Zie voor meer informatie [Toegang verlenen met behulp van SharePoint App-Only](/sharepoint/dev/solution-guidance/security-apponly-azureacs).

Zo wordt app@sharepoint vaak geïdentificeerd als de gebruiker voor de gebeurtenissen 'Uitgevoerde zoekquery' en 'Bestand geopend'. Dat komt doordat een toepassing met SharePoint App-Only-toegang in uw organisatie zoekopdrachten uitvoert en toegang krijgt tot bestanden bij het toepassen van bewaarbeleid op sites en OneDrive-accounts.

Hier zijn een paar andere scenario's waarin app@sharepoint in een auditrecord kan worden geïdentificeerd als de gebruiker die een activiteit heeft uitgevoerd:

- Microsoft 365 Groepen. Wanneer een gebruiker of beheerder een nieuwe groep maakt, worden er auditrecords gegenereerd voor het maken van een siteverzameling, het bijwerken van lijsten en het toevoegen van leden aan een SharePoint-groep. Deze taken worden uitgevoerd namens de gebruiker die de groep heeft gemaakt.

- Microsoft Teams. Net als bij Microsoft 365 Groepen worden auditrecords gegenereerd voor het maken van een siteverzameling, het bijwerken van lijsten en het toevoegen van leden aan een SharePoint-groep wanneer een team wordt gemaakt.

- Nalevingsfuncties. Wanneer een beheerder nalevingsfuncties implementeert, zoals bewaarbeleid, eDiscovery-bewaringen en het automatisch toepassen van vertrouwelijkheidslabels.

In deze en andere scenario's zult u ook opmerken dat meerdere auditrecords met app@sharepoint als de opgegeven gebruiker binnen een kort tijdsbestek zijn gemaakt, vaak binnen een paar seconden na elkaar. Dit geeft ook aan dat ze waarschijnlijk zijn geactiveerd door dezelfde door de gebruiker gestarte taak. De velden ApplicationDisplayName en EventData in de auditrecord kunnen u ook helpen bij het identificeren van het scenario of de toepassing die de gebeurtenis heeft veroorzaakt.

### <a name="folder-activities"></a>Activiteiten in mappen

In de volgende tabel worden de activiteiten in mappen in SharePoint Online en OneDrive voor Bedrijven beschreven. Zoals eerder uitgelegd, geven auditrecords voor sommige SharePoint-activiteiten aan dat de gebruiker app@sharepoint de activiteit heeft uitgevoerd namens de gebruiker of beheerder die de actie heeft gestart. Zie [De gebruiker app\@sharePoint in auditrecords](#the-appsharepoint-user-in-audit-records) voor meer informatie.

|Beschrijvende naam|Bewerking|Beschrijving|
|:-----|:-----|:-----|
|Map gekopieerde|FolderCopied|Gebruiker kopieert een map van een site naar een andere locatie in SharePoint of OneDrive voor Bedrijven.|
|Map gemaakt|FolderCreated|Gebruiker maakt een map op een site.|
|Map verwijderd|FolderDeleted|Gebruiker verwijdert een map van een site. |
|Map verwijderd uit de prullenbak|FolderDeletedFirstStageRecycleBin|Gebruiker verwijdert een map uit de prullenbak op een site.|
|Map verwijderd uit een prullenbak tweede stadium|FolderDeletedSecondStageRecycleBin|Gebruiker verwijdert een map uit de prullenbak tweede stadium op een site.|
|Map gewijzigd|FolderModified|Gebruiker wijzigt een map op een site. Dit geldt ook voor de metagegevens van de map, zoals het wijzigen van labels en eigenschappen.|
|Map verplaatst|FolderMoved|Gebruiker verplaatst een map naar een andere locatie op een site.|
|Naam van map gewijzigd|FolderRenamed|Gebruiker wijzigt de naam van een map op een site.|
|Map teruggezet|FolderRestored|Gebruiker zet een verwijderde map terug vanuit de prullenbak op een site.|
||||

### <a name="sharepoint-list-activities"></a>Activiteiten in de SharePoint-lijst

In de volgende tabel worden de activiteiten beschreven die betrekking hebben op het moment dat gebruikers werken met lijsten en lijstitems in SharePoint Online. Zoals eerder uitgelegd, geven auditrecords voor sommige SharePoint-activiteiten aan dat de gebruiker app@sharepoint de activiteit heeft uitgevoerd namens de gebruiker of beheerder die de actie heeft gestart. Zie [De gebruiker app\@sharePoint in auditrecords](#the-appsharepoint-user-in-audit-records) voor meer informatie.

|Beschrijvende naam|Bewerking|Omschrijving|
|:-----|:-----|:-----|
|Lijst gemaakt|ListCreated|Een gebruiker heeft een SharePoint-lijst gemaakt.|
|Kolom Lijst gemaakt|ListColumnCreated|Een gebruiker heeft een SharePoint-lijstkolom gemaakt. Een lijstkolom is een kolom die is gekoppeld aan een of meer SharePoint-lijsten.|
|Lijstinhoudstype gemaakt|ListContentTypeCreated|Een gebruiker heeft een lijstinhoudstype aangemaakt. Een lijstinhoudstype is een inhoudstype dat is gekoppeld aan een of meer SharePoint-lijsten.|
|Gemaakt lijstitem|ListItemCreated|Een gebruiker heeft een item gemaakt in een bestaande SharePoint-lijst.|
|Sitekolom gemaakt|SiteColumnCreated|Een gebruiker heeft een SharePoint-sitekolom gemaakt. Een sitekolom is een kolom die niet aan een lijst is gekoppeld. Een sitekolom is ook een metagegevensstructuur die kan worden gebruikt door elke lijst op een bepaald web.|
|Site-inhoudstype gemaakt|Site-inhoudstype gemaakt|Een gebruiker heeft een site-inhoudstype gemaakt. Een site-inhoudstype is een inhoudstype dat is gekoppeld aan de bovenliggende site.|
|Verwijderde lijst|ListDeleted|Een gebruiker heeft een SharePoint-lijst verwijderd.|
|Kolom verwijderde lijst|Lijstkolom verwijderd|Een gebruiker heeft een SharePoint-lijstkolom verwijderd.|
|Lijstinhoudstype verwijderd|ListContentTypeDeleted|Een gebruiker heeft een lijstinhoudstype verwijderd.|
|Verwijderd lijstitem|Lijstitem verwijderd|Een gebruiker heeft een SharePoint-lijstitem verwijderd.|
|Sitekolom verwijderd|SiteColumnDeleted|Een gebruiker heeft een SharePoint-sitekolom verwijderd.|
|Site-inhoudstype verwijderd|SiteContentTypeDeleted|Een gebruiker heeft een site-inhoudstype verwijderd.|
|Gerecycled lijstitem|ListItemRecycled|Een gebruiker heeft een SharePoint-lijstitem verplaatst naar de Prullenbak.|
|Herstelde lijst|ListRestored|Een gebruiker heeft een SharePoint-lijst teruggezet vanuit de Prullenbak.|
|Hersteld lijstitem|ListItemRestored|Een gebruiker heeft een SharePoint-lijstitem teruggezet vanuit de Prullenbak.|
|Bijgewerkte lijst|ListUpdated|Een gebruiker heeft een SharePoint-lijst bijgewerkt door een of meer eigenschappen te wijzigen.|
|Bijgewerkte lijstkolom|ListColumnUpdated|Een gebruiker heeft een SharePoint-lijstkolom bijgewerkt door een of meer eigenschappen te wijzigen.|
|Lijstinhoudstype bijgewerkt|ListContentTypeUpdated|Een gebruiker heeft een lijstinhoudstype bijgewerkt door een of meer eigenschappen te wijzigen.|
|Lijstitem bijgewerkt|ListItemUpdated|Een gebruiker heeft een SharePoint-lijstitem bijgewerkt door een of meer eigenschappen te wijzigen.|
|Sitekolom bijgewerkt|SiteColumnUpdated|Een gebruiker heeft een SharePoint-sitekolom bijgewerkt door een of meer eigenschappen te wijzigen.|
|Site-inhoudstype bijgewerkt|SiteContentTypeUpdated|Een gebruiker heeft een site-inhoudstype bijgewerkt door een of meer eigenschappen te wijzigen.|
||||

### <a name="sharing-and-access-request-activities"></a>Activiteiten in verband met delen en aanvragen voor toegang

In de volgende tabel worden de activiteiten in SharePoint Online en OneDrive voor Bedrijven beschreven voor het delen van gebruikers en het aanvragen van toegang. Voor gebeurtenissen in verband met delen wordt de naam van de gebruiker of groep waarmee het item werd gedeeld en of die gebruiker of groep een lid is van of gast is in uw organisatie, aangegeven in de kolom **Detail** onder **Resultaten**. Zie [Auditing voor delen gebruiken in het auditlogboek](use-sharing-auditing.md) voor meer informatie.

> [!NOTE]
> Gebruikers kunnen *leden* of *gasten* zijn, afhankelijk van de eigenschap UserType van het gebruikersobject. Een lid is meestal een werknemer; een gast is meestal een medewerker van buiten de organisatie. Wanneer een gebruiker een uitnodiging voor delen accepteert (en niet al deel uitmaakt van de organisatie), wordt een gastaccount voor de gebruiker gemaakt in de adreslijst van de organisatie. Als er een account voor de gast in de adreslijst is gemaakt, kunnen er rechtstreeks bronnen met de gebruiker worden gedeeld (zonder dat daarvoor een uitnodiging is vereist).

|Beschrijvende naam|Bewerking|Omschrijving|
|:-----|:-----|:-----|
|Machtigingsniveau aan een siteverzameling toegevoegd|PermissionLevelAdded|Een machtigingsniveau is toegevoegd aan een siteverzameling.|
|Aanvraag voor toegang geaccepteerd|AccessRequestAccepted|Een aanvraag voor toegang tot een site, map of document is geaccepteerd en de aanvrager is toegang verleend.|
|Uitnodiging voor delen geaccepteerd|SharingInvitationAccepted|Gebruiker (lid of gast) heeft een uitnodiging voor delen geaccepteerd en is toegang tot een bron verleend. Deze gebeurtenis omvat informatie over de gebruiker die is uitgenodigd en het e-mailadres dat is gebruikt om de uitnodiging te accepteren (deze kunnen verschillend zijn). Deze activiteit gaat vaak gepaard met een tweede gebeurtenis, die beschrijft hoe de gebruiker toegang tot de bron is verleend, bijvoorbeeld dat de gebruiker is toegevoegd aan een groep die toegang tot de bron heeft.|
|Geblokkeerde uitnodiging voor delen|SharingInvitationBlocked|Een uitnodiging tot delen die is verzonden door een gebruiker in uw bedrijf is geblokkeerd door beleid voor het extern delen waarmee extern delen wordt toegestaan of geweigerd op basis van het domein van de doelgebruiker. In dit geval is de uitnodiging tot delen geblokkeerd, omdat: <br/> Het domein van de doelgebruiker is niet opgenomen in de lijst met toegestane domeinen. <br/> Of <br/> Het domein van de doelgebruiker is opgenomen in de lijst met geblokkeerde domeinen. <br/> Zie [Domeinen met beperkingen delen in SharePoint Online en OneDrive voor Bedrijven](/sharepoint/restricted-domains-sharing) voor meer informatie over het toestaan of blokkeren van extern delen op basis van domeinen.|
|Aanvraag voor toegang gemaakt|AccessRequestCreated|Gebruiker vraagt toegang tot een site, map of document waarvoor hij geen machtigingen heeft.|
|In hele bedrijf deelbare koppeling gemaakt|CompanyLinkCreated|Gebruiker heeft een in het hele bedrijf deelbare koppeling gemaakt. koppelingen voor het hele bedrijf kunnen alleen worden gebruikt door leden van uw organisatie. Ze kunnen niet door gasten worden gebruikt.|
|Anonieme koppeling gemaakt|AnonymousLinkCreated|Gebruiker heeft een anonieme koppeling naar een bron gemaakt. Iedereen met deze koppeling heeft toegang tot de bron zonder te hoeven worden geverifieerd.|
|Beveiligde koppeling gemaakt|SecureLinkCreated|Er is een beveiligde koppeling voor delen naar dit item gemaakt.|
|Uitnodiging voor delen gemaakt|SharingInvitationCreated|Gebruiker heeft een bron in SharePoint Online of OneDrive voor Bedrijven gedeeld met een gebruiker die niet voorkomt in de adreslijst van uw organisatie. |
|Beveiligde koppeling verwijderd|SecureLinkDeleted|Een beveiligde koppeling voor delen is verwijderd.|
|Aanvraag voor toegang geweigerd |AccessRequestDenied|Aanvraag voor toegang tot een site, map of document is geweigerd.|
|In hele bedrijf deelbare koppeling verwijderd|CompanyLinkRemoved|Gebruiker heeft een in het hele bedrijf deelbare koppeling verwijderd. De koppeling kan niet meer worden gebruikt voor toegang tot de bron.|
|Anonieme koppeling verwijderd|AnonymousLinkRemoved|Gebruiker heeft een anonieme koppeling naar een bron verwijderd. De koppeling kan niet meer worden gebruikt voor toegang tot de bron.|
|Gedeeld bestand, gedeelde map of gedeelde site|SharingSet|Gebruiker (lid of gast) heeft een bestand, map of site in SharePoint of OneDrive voor Bedrijven gedeeld met een gebruiker in de adreslijst van de organisatie. De waarde in de kolom **Detail** van deze activiteit geeft de naam aan van de gebruiker waarmee de bron is gedeeld en of deze gebruiker een lid of een gast is. <br/><br/> Deze activiteit gaat vaak gepaard met een tweede gebeurtenis, die beschrijft hoe de gebruiker toegang tot de bron is verleend, bijvoorbeeld dat de gebruiker is toegevoegd aan een groep die toegang tot de bron heeft.|
|Aanvraag voor toegang bijgewerkt|AccessRequestUpdated|Een aanvraag voor toegang tot een item is bijgewerkt.|
|Anonieme koppeling bijgewerkt |AnonymousLinkUpdated|Gebruiker heeft een anonieme koppeling naar een bron bijgewerkt. Het bijgewerkte veld wordt bij het exporteren van de zoekresultaten opgenomen in de eigenschap EventData.|
|Uitnodiging voor delen bijgewerkt|SharingInvitationUpdated|Een externe uitnodiging voor delen is bijgewerkt.|
|Anonieme koppeling gebruikt|AnonymousLinkUsed|Een anonieme gebruiker heeft een bron geopend door middel van een anonieme koppeling. De identiteit van de gebruiker is mogelijk onbekend, maar u kunt andere gegevens verkrijgen, zoals het IP-adres van de gebruiker.|
|Delen van bestand, map of site ongedaan gemaakt|SharingRevoked|Gebruiker (lid of gast) heeft het delen van een bestand, map of document met een andere gebruiker, ongedaan gemaakt.|
|In hele bedrijf deelbare koppeling gebruikt|CompanyLinkUsed|Gebruiker heeft een bron geopend door middel van een in het hele bedrijf deelbare koppeling.|
|Beveiligde koppeling gebruikt|SecureLinkUsed|Een gebruiker heeft een beveiligde koppeling gebruikt.|
|Gebruiker toegevoegd aan beveiligde koppeling|AddedToSecureLink|Een gebruiker is toegevoegd aan de lijst met entiteiten die een koppeling voor beveiligd delen kunnen gebruiken.|
|Gebruiker uit beveiligde koppeling verwijderd|RemovedFromSecureLink|Een gebruiker is verwijderd uit de lijst met entiteiten die een koppeling voor beveiligd delen kunnen gebruiken.|
|Uitnodiging voor delen ingetrokken|SharingInvitationRevoked|Gebruik heeft een uitnodiging voor delen naar een bron ingetrokken. |
||||

### <a name="synchronization-activities"></a>Synchronisatieactiviteiten

De volgende tabel bevat activiteiten met bestandssynchronisatie in SharePoint Online en OneDrive voor Bedrijven.

|Beschrijvende naam|Bewerking|Beschrijving|
|:-----|:-----|:-----|
|Computer toegestaan bestanden te synchroniseren|ManagedSyncClientAllowed|Gebruiker heeft een synchronisatierelatie met een site tot stand gebracht. De synchronisatierelatie is geslaagd omdat de computer van de gebruiker lid is van een domein dat is toegevoegd aan de lijst met domeinen (de *lijst met veilige geadresseerden*) die toegang hebben tot bibliotheken in de organisatie. <br/><br/> Zie voor meer informatie over deze functie [Windows PowerShell-cmdlets gebruiken om Microsoft OneDrive-synchronisatie voor domeinen die op de lijst met veilige geadresseerden staan](/powershell/module/sharepoint-online/).|
|Computer geblokkeerd voor het synchroniseren van bestanden|UnmanagedSyncClientBlocked|Gebruiker probeert een synchronisatierelatie met een site tot stand te brengen vanaf een computer die geen lid is van het domein van de organisatie of lid van een domein dat is toegevoegd aan de lijst met domeinen (de *lijst met veilige geadresseerden*) die toegang hebben tot bibliotheken in de organisatie. De synchronisatierelatie is niet toegestaan en de computer van de gebruiker wordt geblokkeerd zodat het synchroniseren, downloaden of uploaden van bestanden in een documentbibliotheek niet mogelijk is. <br/><br/> Zie voor meer informatie [Windows PowerShell-cmdlets gebruiken om Microsoft OneDrive-synchronisatie voor domeinen die op de lijst met veilige geadresseerden staan](/powershell/module/sharepoint-online/).|
|Bestanden naar computer gedownload|FileSyncDownloadedFull|Gebruiker breng een synchronisatierelatie tot stand en downloadt voor het eerst bestanden naar de computer vanuit een documentbibliotheek.|
|Bestandswijzigingen naar computer gedownload|FileSyncDownloadedPartial|Gebruiker heeft wijzigingen aan bestanden vanaf een documentbibliotheek gedownload. Deze activiteit geeft aan dat wijzigingen aan bestanden in de documentbibliotheek zijn gedownload naar de computer van de gebruiker. Alleen wijzigingen zijn gedownload omdat de documentbibliotheek eerder door de gebruiker is gedownload (zoals aangegeven door de activiteit **Bestanden naar computer gedownload**).|
|Bestanden naar documentbibliotheek geüpload|FileSyncUploadedFull|Gebruiker breng een synchronisatierelatie tot stand en uploadt voor het eerst bestanden naar een documentbibliotheek vanaf de computer.|
|Bestandswijzigingen naar documentbibliotheek geüpload|FileSyncUploadedPartial|Gebruiker heeft bestandswijzigingen naar een documentbibliotheek geüpload. Deze gebeurtenis geeft aan dat wijzigingen in de lokale versie van een bestand in een documentbibliotheek naar de documentbibliotheek zijn geüpload. Alleen wijzigingen worden geüpload omdat deze bestanden eerder door de gebruiker zijn geüpload (zoals aangegeven door de activiteit **Bestanden naar documentbibliotheek geüpload**).|
||||

### <a name="site-permissions-activities"></a>Activiteiten voor sitemachtigingen

De volgende tabel bevat gebeurtenissen die betrekking hebben op het toewijzen van machtigingen in SharePoint en het gebruik van groepen om toegang tot sites te verlenen (en in te trekken). Zoals eerder uitgelegd, geven auditrecords voor sommige SharePoint-activiteiten aan dat de gebruiker app@sharepoint de activiteit heeft uitgevoerd namens de gebruiker of beheerder die de actie heeft gestart. Zie [De gebruiker app\@sharePoint in auditrecords](#the-appsharepoint-user-in-audit-records) voor meer informatie.

|Beschrijvende naam|Bewerking|Omschrijving|
|:-----|:-----|:-----|
|Beheerder van siteverzameling toegevoegd|SiteCollectionAdminAdded|Beheerder of eigenaar van siteverzameling voegt een persoon toe als beheerder van de siteverzameling voor een site. Beheerders van siteverzamelingen hebben machtigingen voor volledig beheer van de siteverzameling en alle subsites. Deze activiteit wordt ook geregistreerd wanneer een beheerder zichzelf toegang geeft tot het OneDrive-account van een gebruiker (door het gebruikersprofiel te bewerken in het SharePoint-beheercentrum of door [het Microsoft 365-beheercentrum te gebruiken](/office365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)).|
|Gebruiker of groep aan SharePoint-groep toegevoegd|AddedToGroup|Gebruiker heeft een lid of gast aan een SharePoint-groep toegevoegd. Dit kan een bewuste actie zijn of het gevolg van een andere activiteit, zoals een gebeurtenis voor delen.|
|Machtigingsniveau voor overname onderbroken|PermissionLevelsInheritanceBroken|Een item is gewijzigd zodat dit niet meer de machtigingsniveaus van de bovenliggende site overneemt.|
|Deelmachtiging voor overname onderbroken|SharingInheritanceBroken|Een item is gewijzigd zodat het niet langer machtigingen voor delen overneemt van het bovenliggende item.|
|Groep gemaakt|GroupAdded|Sitebeheerder of eigenaar maakt een groep voor een site of voert een taak uit waardoor een groep wordt gemaakt. Als een gebruiker bijvoorbeeld de eerste keer een koppeling maakt om een bestand te delen, wordt er een systeemgroep toegevoegd aan de OneDrive voor Bedrijven-site van de gebruiker. Deze gebeurtenis kan ook optreden als een gebruiker een koppeling met bewerkingsrechten voor een gedeeld bestand heeft gemaakt.|
|Groep verwijderd|GroupRemoved|Gebruiker verwijdert een groep van een site. |
|Instelling voor toegangsaanvragen gewijzigd|WebRequestAccessModified|De instellingen voor toegangsaanvragen zijn op een site gewijzigd.|
|Instelling voor Leden kunnen delen gewijzigd|WebMembersCanShareModified|De instelling voor **Leden kunnen delen** is op een site gewijzigd.|
|Machtigingsniveau van siteverzameling gewijzigd|PermissionLevelModified|Een machtigingsniveau van een siteverzameling is gewijzigd.|
|Sitemachtigingen gewijzigd|SitePermissionsModified|Sitebeheerder of eigenaar (of systeemaccount) wijzigt het machtigingsniveau dat aan een groep op een site is verleend. Deze activiteit wordt ook in het logboek geregistreerd als alle machtigingen van een groep zijn verwijderd. <br/><br/> **OPMERKING**: deze bewerking is afgeschaft in SharePoint Online. Als u verwante gebeurtenissen zoekt, kunt u zoeken naar andere activiteiten die te maken hebben met machtigingen zoals **Beheerder van siteverzameling toegevoegd**, **Gebruiker of groep toegevoegd aan SharePoint-groep**, **Gebruiker toegestaan om groepen te maken**, **Groep gemaakt** en **Groep verwijderd**.|
|Machtigingsniveau van siteverzameling verwijderd|PermissionLevelRemoved|Een machtigingsniveau van een siteverzameling is verwijderd.|
|Beheerder van siteverzameling verwijderd|SiteCollectionAdminRemoved|Beheerder of eigenaar van siteverzameling verwijdert een persoon als beheerder van een siteverzameling voor een site. Deze activiteit wordt ook geregistreerd wanneer een beheerder zichzelf verwijdert uit de lijst met beheerders van siteverzamelingen voor het OneDrive-account van een gebruiker (door het gebruikersprofiel te bewerken in het SharePoint-beheercentrum).  Als u deze activiteit wilt retourneren in de zoekresultaten van het auditlogboek, moet u zoeken naar alle activiteiten.|
|Gebruiker of groep uit SharePoint-groep verwijderd|RemovedFromGroup|Gebruiker heeft een lid of gast uit een SharePoint-groep verwijderd. Dit kan een bewuste actie zijn of het gevolg van een andere activiteit, bijvoorbeeld als een deelactiviteit ongedaan wordt gemaakt.|
|Machtigingen voor sitebeheer aangevraagd|SiteAdminChangeRequest|Gebruiker vraagt te worden toegevoegd als beheerder van siteverzameling voor een siteverzameling. Beheerders van siteverzamelingen hebben machtigingen voor volledig beheer van de siteverzameling en alle subsites.|
|Deelmachtiging voor overname hersteld|SharingInheritanceReset|Er is een wijziging toegepast, zodat een item de deelmachtigingen van de bovenliggende site overneemt.|
|Groep bijgewerkt|GroupUpdated|Sitebeheerder of eigenaar wijzigt de instellingen van een groep voor een site. Dit kan het volgende inhouden: het wijzigen van de groepsnaam, wie het groepslidmaatschap kan bekijken of bewerken, of hoe aanvragen voor lidmaatschappen worden afgehandeld.|
||||

### <a name="site-administration-activities"></a>Activiteiten in verband met sitebeheer

De volgende tabel bevat de gebeurtenissen die het gevolg zijn van sitebeheertaken in SharePoint Online. Zoals eerder uitgelegd, geven auditrecords voor sommige SharePoint-activiteiten aan dat de gebruiker app@sharepoint de activiteit heeft uitgevoerd namens de gebruiker of beheerder die de actie heeft gestart. Zie [De gebruiker app\@sharePoint in auditrecords](#the-appsharepoint-user-in-audit-records) voor meer informatie.

|Beschrijvende naam|Bewerking|Omschrijving|
|:-----|:-----|:-----|
|Toegestane gegevenslocatie toegevoegd|AllowedDataLocationAdded|Een SharePoint-beheerder of globale beheerder heeft een toegestane gegevenslocatie toegevoegd in een omgeving met meerdere geografische locaties.|
|Vrijgestelde gebruikersagent toegevoegd|ExemptUserAgentSet|Een SharePoint-beheerder of globale beheerder voegt een gebruikersagent toe aan de lijst met vrijgestelde gebruikersagenten in het SharePoint-beheercentrum. |
|Beheerder van geografische locatie toegevoegd|GeoAdminAdded|Een SharePoint-beheerder of globale beheerder heeft een gebruiker toegevoegd als geobeheerder van een locatie.|
|Gebruiker toegestaan groepen te maken|AllowGroupCreationSet|Sitebeheerder of eigenaar voegt een machtigingsniveau toe aan een site waardoor een gebruiker aan wie de machtiging wordt verleend, een groep voor die site kan maken. |
|Geografische verplaatsing van geannuleerde site|SiteGeoMoveCancelled|Een SharePoint-beheerder of globale beheerder annuleert de geografische verplaatsing van een SharePoint- of OneDrive-site. Met de functie Multi-Geo kan een organisatie meerdere geografische gebieden van het Microsoft-datacenter omspannen. Dit worden geografische gebieden genoemd. Zie voor meer informatie [mogelijkheden voor Multi-Geo in OneDrive en SharePoint Online](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md).|
|Beleid voor delen gewijzigd|SharingPolicyChanged|Een SharePoint-beheerder of globale beheerder heeft een SharePoint-beleid voor delen gewijzigd met behulp van de Microsoft 365-beheerportal, SharePoint-beheerportal of SharePoint Online Management Shell. Elke wijziging aan de instellingen in de beleidsregel voor delen in de organisatie wordt in het logboek geregistreerd. Het gewijzigde beleid wordt aangegeven in het veld **ModifiedProperties** in de gedetailleerde eigenschappen van de gebeurtenisrecord.|
|Toegangsbeleid voor apparaten is gewijzigd|DeviceAccessPolicyChanged|Een SharePoint-beheerder of globale beheerder heeft het beleid voor niet-beheerde apparaten van uw bedrijf gewijzigd. Dit beleid bepaalt de toegang tot SharePoint, OneDrive en Microsoft 365 van apparaten die geen deel van uw bedrijf uitmaken. Het configureren van dit beleid vereist een Enterprise Mobility + Security-abonnement. Zie voor meer informatie [Control access from unmanaged devices (Toegangsbeheer op niet-beheerde apparaten)](/sharepoint/control-access-from-unmanaged-devices).|
|Vrijgestelde gebruikersagenten gewijzigd|CustomizeExemptUsers|Een SharePoint- of globale beheerder heeft de lijst met vrijgestelde gebruikersagenten aangepast in het SharePoint-beheercentrum. U kunt opgeven welke gebruikersagenten moeten worden vrijgesteld van het ontvangen van een hele webpagina die moet worden geïndexeerd. Dit betekent dat als een door u vrijgestelde gebruikersagent een InfoPath-formulier krijgt, het formulier wordt geretourneerd als een XML-bestand in plaats van een hele webpagina. Hierdoor kunnen de InfoPath-formulieren sneller worden geïndexeerd.|
|Toegangsbeleid voor netwerk gewijzigd|NetworkAccessPolicyChanged|Een SharePoint-beheerder of globale beheerder heeft het beleid op basis van locatie gewijzigd (ook wel een vertrouwde netwerkgrens genoemd) in het SharePoint-beheercentrum of met behulp van SharePoint Online PowerShell. Dit type beleid beheert wie toegang heeft tot SharePoint- en OneDrive-bronnen in uw bedrijf op basis van geautoriseerde IP-adresbereiken die u opgeeft. Zie [Toegang tot SharePoint Online en OneDrive-gegevens regelen op basis van netwerklocaties](/sharepoint/control-access-based-on-network-location) voor meer informatie.|
|Geografische verplaatsing van site voltooid|SiteGeoMoveCompleted|Een geografische verplaatsing van een site die was gepland door een globale beheerder in uw bedrijf is voltooid. Met de functie Multi-Geo kan een organisatie meerdere geografische gebieden van het Microsoft-datacenter omspannen. Dit worden geografische gebieden genoemd. Zie voor meer informatie [Multi-Geo-mogelijkheden in OneDrive en SharePoint Online in Office 365](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md).|
|Verzonden-naar-verbinding gemaakt|SendToConnectionAdded|Een SharePoint-beheerder of globale beheerder maakt een nieuwe Verzenden-naar-verbinding op de pagina Recordbeheer in het SharePoint-beheercentrum. Een Verzenden-naar-verbinding geeft de instellingen op voor een documentopslag of recordcentrum. Als u een Verzonden-naar-verbinding maakt, kan Inhoudsbeheer documenten naar een specifieke locatie verzenden. |
|Siteverzameling gemaakt|SiteCollectionCreated|Een SharePoint-beheerder of globale beheerder maakt een siteverzameling in uw SharePoint Online-organisatie of een gebruiker maakt een OneDrive voor Bedrijven-site.|
|Verwijderde zwevende hubsite|HubSiteOrphanHubDeleted|Een SharePoint-beheerder of globale beheerder heeft een zwevende hubsite verwijderd. Dit is een hubsite waaraan geen sites zijn gekoppeld. Een zwevende hub wordt waarschijnlijk veroorzaakt door het verwijderen van de oorspronkelijke hubsite.|
|Verzonden-naar-verbinding verwijderd|SendToConnectionRemoved|Een SharePoint-beheerder of globale beheerder verwijdert een nieuwe Verzenden-naar-verbinding op de pagina Recordbeheer in het SharePoint-beheercentrum.|
|Site verwijderd|SiteDeleted|Sitebeheerder verwijdert een site.|
|Voorbeeldweergave van documenten ingeschakeld|PreviewModeEnabledSet|Sitebeheerder schakelt voorbeeldweergave van documenten voor een site in.|
|Oude werkstroom ingeschakeld|LegacyWorkflowEnabledSet|Sitebeheerder of eigenaar voegt het inhoudstype SharePoint 2013-werkstroomtaak aan de site toe. Hoofdbeheerders kunnen in het SharePoint-beheercentrum ook werkstromen voor de hele organisatie inschakelen.|
|Office op aanvraag ingeschakeld|OfficeOnDemandSet|Sitebeheerder schakelt Office op aanvraag in, waardoor gebruikers de nieuwste versie van Office-bureaubladtoepassingen kunnen openen. Office op aanvraag wordt ingeschakeld in het SharePoint-beheercentrum. Hiervoor is een Microsoft 365-abonnement vereist dat volledige, geïnstalleerde Office-toepassingen bevat.|
|Resultatenbron voor zoekopdrachten naar personen ingeschakeld|PeopleResultsScopeSet|Sitebeheerder maakt de resultatenbron voor zoekopdrachten naar personen voor een site.|
|RSS-feeds ingeschakeld|NewsFeedEnabledSet|Sitebeheerder of eigenaar schakelt RSS-feeds voor een site in. Hoofdbeheerders kunnen in het SharePoint-beheercentrum RSS-feeds voor de hele organisatie inschakelen.|
|Site toegevoegd aan hubsite|HubSiteJoined|Een site-eigenaar koppelt zijn of haar site aan een hubsite.|
|Hubsite geregistreerd|HubSiteRegistered|Een SharePoint-beheerder of globale beheerder maakt een hubsite. Het resultaat is dat de site wordt geregistreerd als hubsite.|
|Toegestane gegevenslocatie verwijderd|AllowedDataLocationDeleted|Een SharePoint-beheerder of globale beheerder heeft een toegestane gegevenslocatie in een omgeving met meerdere geografische locaties verwijderd.|
|Beheerder van geografische locatie verwijderd|GeoAdminDeleted|Een SharePoint-beheerder of globale beheerder heeft een gebruiker verwijderd als geobeheerder van een locatie.|
|Naam van site gewijzigd|SiteRenamed|Sitebeheerder of eigenaar wijzigt de naam van een site|
|Geplande geografische verplaatsing van site|SiteGeoMoveScheduled|Een SharePoint-beheerder of globale beheerder plant met succes de geografische verplaatsing van een SharePoint- of OneDrive-site. Met de functie Multi-Geo kan een organisatie meerdere geografische gebieden van het Microsoft-datacenter omspannen. Dit worden geografische gebieden genoemd. Zie voor meer informatie [Multi-Geo-mogelijkheden in OneDrive en SharePoint Online in Office 365](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md).|
|Hostsite ingesteld|HostSiteSet|Een SharePoint-beheerder of globale beheerder wijzigt de aangewezen site voor het hosten van persoonlijke of OneDrive voor Bedrijven-sites. |
|Opslagquota voor geografische locatie ingesteld|GeoQuotaAllocated|Een SharePoint-beheerder of globale beheerder heeft het opslagquotum geconfigureerd voor een geografische locatie in een omgeving met meerdere geografische locaties.|
|Niet-aaneengeplaatste site vanaf hubsite|HubSiteUnjoined|Een site-eigenaar ontkoppelt zijn of haar site van een hubsite.|
|Hubsite-registratie ongedaan gemaakt|HubSiteUnregistered|Een SharePoint-beheerder of globale beheerder heeft de registratie van een site ongedaan gemaakt als hubsite. Wanneer de registratie van een hubsite wordt ongedaan gemaakt, werkt deze niet meer als hubsite.|
||||

### <a name="exchange-mailbox-activities"></a>Activiteiten in verband met Exchange-postvakken

De volgende tabel bevat de activiteiten die kunnen worden geregistreerd door auditlogregistratie voor postvakken. Postvakactiviteiten die zijn uitgevoerd door de eigenaar van het postvak, een gedelegeerde gebruiker of een beheerder, worden automatisch tot 90 dagen in het auditlogboek geregistreerd. Het is mogelijk voor een beheerder om controlelogboekregistratie van postvakken uit te schakelen voor alle gebruikers in uw organisatie. In dit geval worden er geen postvakacties voor een gebruiker geregistreerd. Zie [Postvakcontrole beheren](enable-mailbox-auditing.md) voor meer informatie.

 U kunt ook zoeken naar postvakactiviteiten met behulp van het cmdlet [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) in Exchange Online PowerShell.

|Beschrijvende naam|Bewerking|Omschrijving|
|:-----|:-----|:-----|
|Toegang tot postvakitems|MailItemsAccessed|Berichten zijn gelezen of toegankelijk in het postvak. Controlerecords voor deze activiteit worden op twee manieren geactiveerd: wanneer een e-mailclient (zoals Outlook) een afhankelijke bewerking uitvoert op berichten of wanneer e-mailprotocollen (zoals Exchange ActiveSync of IMAP) items in een e-mailmap synchroniseren. Deze activiteit wordt alleen geregistreerd voor gebruikers met een licentie voor Office 365 of Microsoft 365 E5. Het analyseren van controlerecords voor deze activiteit is handig bij het onderzoeken van een gehackt e-mailaccount. Zie voor meer informatie de sectie 'Toegang tot belangrijke gebeurtenissen voor onderzoeken' in [Geavanceerde audit](advanced-audit.md#access-to-crucial-events-for-investigations). |
|Postvakmachtigingen voor gedelegeerde toegevoegd|Add-MailboxPermission|De beheerder heeft de postvakmachtiging FullAccess aan een gebruiker toegewezen (ook wel gedelegeerde genoemd) voor toegang tot het postvak van een andere persoon. Met de machtiging FullAccess kan de gedelegeerde het postvak van een andere persoon openen en de inhoud ervan lezen en beheren.|
|Gebruiker met gemachtigdentoegang tot agendamap toegevoegd of verwijderd|UpdateCalendarDelegation|Een gebruiker is toegevoegd of verwijderd als gedelegeerde aan de agenda van het postvak van een andere gebruiker. Agendadelegering geeft iemand anders in dezelfde organisatie machtigingen voor het beheren van de agenda van de eigenaar van het postvak.|
|Machtigingen voor map toegevoegd|AddFolderPermissions(AddFolderPermissions)|Een mapmachtiging werd toegevoegd. Mapmachtigingen bepalen welke gebruikers in uw organisatie toegang hebben tot mappen in een mailbox en tot de berichten in die mappen.|
|Berichten naar een andere map gekopieerd|Kopiëren|Er is een bericht naar een andere map gekopieerd.|
|Gemaakt postvakitem|Maken|Er is een item gemaakt in de map Agenda, Contactpersonen, Notities of Taken van het postvak. Er wordt bijvoorbeeld een nieuw vergaderverzoek gemaakt. Het maken, verzenden of ontvangen van een bericht wordt niet gecontroleerd. Ook het maken van een postvak wordt niet gecontroleerd.|
|Nieuwe regel voor Postvak IN gemaakt in Outlook Web App|New-InboxRule|Een eigenaar van een postvak of een andere gebruiker met toegang tot het postvak heeft een regel voor Postvak IN gemaakt in de Outlook Web App.|
|Berichten verwijderd uit de map Verwijderde items|SoftDelete|Een bericht is definitief verwijderd of verwijderd uit de map Verwijderde items. Deze items worden verplaatst naar de map Herstelbare items. Berichten worden ook verplaatst naar de map Herstelbare items als een gebruiker de map selecteert en op **Shift+Delete** drukt.|
|Gelabeld bericht als record|ApplyRecordLabel|Een bericht werd geclassificeerd als vertrouwelijk. Dit gebeurt wanneer een bewaarlabel dat inhoud classificeert als een record, handmatig of automatisch wordt toegepast op een bericht.|
|Berichten naar een andere map verplaatst|Move|Een bericht is naar een andere map verplaatst.|
|Berichten verplaatst naar map Verwijderde Items|MoveToDeletedItems|Een bericht is verwijderd en verplaatst naar de map Verwijderde items.|
|Mapmachtiging gewijzigd|UpdateFolderPermissions|Een mapmachtiging is gewijzigd. Met mapmachtigingen bepaalt u welke gebruikers in uw organisatie toegang hebben tot postvakmappen en de berichten die erin staan.|
|Gewijzigde regel voor Postvak IN vanuit Outlook Web App|Set-InboxRule|Een eigenaar van een postvak of een andere gebruiker met toegang tot het postvak heeft een regel voor Postvak IN gemaakt in de Outlook Web App.|
|Bericht is definitief uit het postvak verwijderd|HardDelete|Een bericht is verwijderd uit de map Herstelbare items (definitief verwijderd uit het postvak)|
|Postvakmachtigingen voor gedelegeerde verwijderd|Remove-MailboxPermission|Een beheerder heeft de machtiging FullAccess (die was toegewezen aan een gedelegeerde) verwijderd uit het postvak van een persoon. Nadat de machtiging FullAccess is verwijderd, kan de gedelegeerde het postvak van de andere persoon niet meer openen. De gedelegeerde heeft dan geen toegang meer tot de inhoud ervan.|
|Machtigingen uit map verwijderd|RemoveFolderPermissions|Een mapmachtiging werd verwijderd. Mapmachtigingen bepalen welke gebruikers in uw organisatie toegang hebben tot mappen in een mailbox en tot de berichten in die mappen.|
|Verzonden bericht|Verzenden|Er is een bericht verzonden, beantwoord of doorgestuurd. Deze activiteit wordt alleen geregistreerd voor gebruikers met een licentie voor Office 365 of Microsoft 365 E5. Zie voor meer informatie de sectie 'Toegang tot belangrijke gebeurtenissen voor onderzoeken' in [Geavanceerde audit](advanced-audit.md#access-to-crucial-events-for-investigations).|
|Bericht verzonden met machtiging Verzenden als |SendAs|Een bericht is verzonden met de machtiging Verzenden als. Dit betekent dat een andere gebruiker het bericht heeft verzonden zodat het lijkt alsof het afkomstig is van de eigenaar van het postvak.|
|Bericht verzonden met machtiging Verzenden namens|SendOnBehalf|Een bericht is verzonden met de machtiging Verzenden namens. Dit betekent dat een andere gebruiker het bericht heeft verzonden namens de eigenaar van het postvak. Het bericht maakt de geadresseerde duidelijk namens wie het bericht is verzonden en wie het bericht feitelijk heeft verzonden.|
|Bijgewerkte regels voor Postvak IN van Outlook-client|UpdateInboxRules|Een eigenaar van een postvak of een andere gebruiker met toegang tot het postvak heeft een regel voor Postvak IN gewijzigd in de Outlook-client.|
|Bericht bijgewerkt|Update|Een bericht (of de eigenschappen ervan) is (zijn) gewijzigd.|
|Gebruiker is aangemeld bij postvak|MailboxLogin|De gebruiker heeft zich aangemeld bij zijn of haar postvak.|
|Bericht labelen als record||Een gebruiker heeft een bewaarlabel toegepast op een e-mailbericht. Dit label is geconfigureerd om het item als een record te markeren. |
||||

### <a name="user-administration-activities"></a>Activiteiten in verband met gebruikersbeheer

De volgende tabel bevat activiteiten in verband met gebruikersbeheer die worden geregistreerd als een beheerder een gebruikersaccount toevoegt of wijzigt via het Microsoft 365-beheercentrum of de Azure-beheerportal.

> [!NOTE]
> De namen van de bewerking die worden vermeld in de kolom **Bewerking** in de volgende tabel, bevatten een punt ( `.` ). U moet de periode opnemen in de naam van de bewerking als u de bewerking opgeeft in een PowerShell-opdracht bij het zoeken in het auditlogboek, het maken van controle bewaarbeleid, het maken van waarschuwingsbeleid of het maken van activiteitswaarschuwingen. Zorg er ook voor dat u dubbele aanhalingstekens (`" "`) gebruikt om de naam van de bewerking te bevatten.

|Activiteit|Bewerking|Beschrijving|
|:-----|:-----|:-----|
|Gebruiker toegevoegd|Gebruiker toevoegen.|Er is een gebruikersaccount gemaakt.|
|Gebruikerslicentie gewijzigd|Gebruikerslicentie wijzigen.|De aan een gebruiker verleende licentie is gewijzigd. Als u wilt weten welke licenties zijn gewijzigd, raadpleegt u de betreffende activiteit **Gebruiker bijgewerkt**.|
|Gebruikerswachtwoord gewijzigd|Gebruikerswachtwoord wijzigen.|Een gebruiker wijzigt zijn of haar wachtwoord. Selfservice voor wachtwoord opnieuw instellen moet zijn ingeschakeld (voor alle of geselecteerde gebruikers) in uw organisatie, zodat gebruikers hun wachtwoord opnieuw kunnen instellen. U kunt ook activiteit voor het zelf opnieuw instellen van wachtwoorden bijhouden in Azure Active Directory. Zie [Rapportageopties voor Microsoft Azure AD-wachtwoordbeheer](/azure/active-directory/authentication/howto-sspr-reporting) voor meer informatie.
|Gebruiker verwijderd|Gebruiker verwijderen.|Er is een gebruikersaccount verwijderd.|
|Wachtwoord van de gebruiker opnieuw instellen|Wachtwoord van de gebruiker opnieuw instellen.|Beheerder heeft het wachtwoord voor een gebruiker opnieuw ingesteld.|
|Eigenschap ingesteld waardoor een gebruiker wordt gedwongen het wachtwoord te wijzigen|Gebruikerswachtwoord wijzigen afdwingen instellen.|Beheerder heeft de eigenschap ingesteld waardoor een gebruiker wordt gedwongen het wachtwoord te wijzigen zodra de gebruiker zich de volgende keer bij Office 365 aanmeldt.|
|Licentie-eigenschappen instellen|Licentie-eigenschappen instellen.|Beheerder wijzigt de eigenschappen van een aan een gebruiker verleende licentie.|
|Gebruiker bijgewerkt|Gebruiker bijwerken.|Een beheerder wijzigt een of meer eigenschappen van een gebruikersaccount. Zie de sectie Update user attributes (Gebruikerskenmerken bijwerken) in [Azure Active Directory Audit Report Events](/azure/active-directory/reports-monitoring/concept-audit-logs) (Gebeurtenissen in het Azure Active Directory-auditrapport) voor een lijst met de gebruikerseigenschappen die kunnen worden bijgewerkt.|
||||

### <a name="azure-ad-group-administration-activities"></a>Activiteiten in verband met groepsbeheer via Microsoft Azure AD

De volgende tabel bevat activiteiten in verband met groepsbeheer die worden geregistreerd als een beheerder of gebruiker een Microsoft 365-groep maakt of wijzigt of als een beheerder een beveiligingsgroep maakt via het Microsoft 365-beheercentrum of de Azure-beheerportal. Zie voor meer informatie over groepen in Office 365 [Groepen weergeven, maken en verwijderen in het Microsoft 365-beheercentrum](../admin/create-groups/create-groups.md).

> [!NOTE]
> De namen van de bewerking die worden vermeld in de kolom **Bewerking** in de volgende tabel, bevatten een punt ( `.` ). U moet de periode opnemen in de naam van de bewerking als u de bewerking opgeeft in een PowerShell-opdracht bij het zoeken in het auditlogboek, het maken van controle bewaarbeleid, het maken van waarschuwingsbeleid of het maken van activiteitswaarschuwingen. Zorg er ook voor dat u dubbele aanhalingstekens (`" "`) gebruikt om de naam van de bewerking te bevatten.

|Beschrijvende naam|Bewerking|Beschrijving|
|:-----|:-----|:-----|
|Groep toegevoegd|Groep toevoegen.|Er is een groep gemaakt.|
|Lid aan groep toegevoegd|Lid aan groep toevoegen.|Er is een lid aan een groep toegevoegd.|
|Groep verwijderd|Groep verwijderen.|Er is een groep verwijderd.|
|Lid uit groep verwijderd|Lid uit groep verwijderen.|Er is een lid uit een groep verwijderd.|
|Groep bijgewerkt|Groep bijwerken.|Er is een eigenschap van de groep gewijzigd.|
||||

### <a name="application-administration-activities"></a>Activiteiten in verband met toepassingsbeheer

De volgende tabel bevat beheeractiviteiten van toepassingen die worden geregistreerd als een beheerder een toepassing toevoegt of wijzigt die in Azure Active Directory is geregistreerd. Alle toepassingen die van Azure Active Directory afhankelijk zijn voor verificatie moeten in de directory worden geregistreerd.

> [!NOTE]
> De namen van de bewerking die worden vermeld in de kolom **Bewerking** in de volgende tabel, bevatten een punt ( `.` ). U moet de periode opnemen in de naam van de bewerking als u de bewerking opgeeft in een PowerShell-opdracht bij het zoeken in het auditlogboek, het maken van controle bewaarbeleid, het maken van waarschuwingsbeleid of het maken van activiteitswaarschuwingen. Zorg er ook voor dat u dubbele aanhalingstekens (`" "`) gebruikt om de naam van de bewerking te bevatten.

|Beschrijvende naam|Bewerking|Beschrijving|
|:-----|:-----|:-----|
|Overdrachtsvermelding toegevoegd|Overdrachtsvermelding toevoegen.|Een machtiging voor verificatie is gemaakt voor/verleend aan een toepassing in Azure Active Directory. |
|Service-principal toegevoegd|Service-principal toevoegen.|Er is een toepassing geregistreerd in Azure Active Directory. Een toepassing wordt in de directory voorgesteld door een service-principal.|
|Referenties voor een service-principal toegevoegd |Referenties voor een service-principal toevoegen.|Er zijn referenties toegevoegd voor een service-principal in Azure Active Directory. Een service-principal stelt een toepassing in de directory voor.|
|Overdrachtsvermelding verwijderd|Overdrachtsvermelding verwijderen.|Een machtiging voor verificatie is verwijderd uit een toepassing in Azure Active Directory. |
|Service-principal uit de directory verwijderd|Service-principal verwijderen.|Er is een toepassing uit Azure Active Directory verwijderd of de registratie ervan is ongedaan gemaakt. Een toepassing wordt in de directory voorgesteld door een service-principal.|
|Referenties uit een service-principal verwijderd |Referenties uit een service-principal verwijderen.|Er zijn referenties verwijderd uit een service-principal in Azure Active Directory. Een service-principal stelt een toepassing in de directory voor.|
|Overdrachtsvermelding instellen|Overdrachtsvermelding instellen.|Een machtiging voor verificatie is bijgewerkt voor een toepassing in Azure Active Directory. |
||||

### <a name="role-administration-activities"></a>Activiteiten in verband met rolbeheer

De volgende tabel bevat activiteiten van rolbeheer in Azure Active Directory die worden geregistreerd als een beheerder beheerrollen beheert in het Microsoft 365-beheercentrum of in de Azure-beheerportal.

> [!NOTE]
> De namen van de bewerking die worden vermeld in de kolom **Bewerking** in de volgende tabel, bevatten een punt ( `.` ). U moet de periode opnemen in de naam van de bewerking als u de bewerking opgeeft in een PowerShell-opdracht bij het zoeken in het auditlogboek, het maken van controle bewaarbeleid, het maken van waarschuwingsbeleid of het maken van activiteitswaarschuwingen. Zorg er ook voor dat u dubbele aanhalingstekens (`" "`) gebruikt om de naam van de bewerking te bevatten.

|Beschrijvende naam|Bewerking|Beschrijving|
|:-----|:-----|:-----|
|Lid aan rol toevoegen|Lid aan rol toevoegen.|Er is een gebruiker toegevoegd aan een beheerrol in Microsoft 365. |
|Gebruiker uit directoryrol verwijderd |Lid uit rol verwijderen.|Er is een gebruiker verwijderd uit de beheerrol in Microsoft 365.|
|Contactgegevens van bedrijf ingesteld|Contactgegevens van bedrijf ingesteld.|De contactvoorkeuren op bedrijfsniveau zijn bijgewerkt voor uw organisatie, waaronder e-mailadressen voor abonnements-e-mail die door Microsoft 365 wordt verzonden en technische meldingen over services.|
||||

### <a name="directory-administration-activities"></a>Activiteiten in verband met adreslijstbeheer

De volgende tabel geeft een overzicht van de Azure AD-directory en domeingerelateerde activiteiten die worden geregistreerd wanneer een beheerder zijn organisatie beheert in het Microsoft 365-beheercentrum of in de Azure-beheerportal.

> [!NOTE]
> De namen van de bewerking die worden vermeld in de kolom **Bewerking** in de volgende tabel, bevatten een punt ( `.` ). U moet de periode opnemen in de naam van de bewerking als u de bewerking opgeeft in een PowerShell-opdracht bij het zoeken in het auditlogboek, het maken van controle bewaarbeleid, het maken van waarschuwingsbeleid of het maken van activiteitswaarschuwingen. Zorg er ook voor dat u dubbele aanhalingstekens (`" "`) gebruikt om de naam van de bewerking te bevatten.

|Beschrijvende naam|Bewerking|Beschrijving|
|:-----|:-----|:-----|
|Domein aan bedrijf toegevoegd|Domein aan bedrijf toevoegen.|Er is een domein toegevoegd aan uw organisatie.|
|Er is een partner aan de directory toegevoegd|Partner aan de directory toevoegen.|Er is een partner (gedelegeerde beheerder) aan de uw organisatie toegevoegd.|
|Domein uit bedrijf verwijderd|Domein uit bedrijf verwijderen.|Er is een domein verwijderd uit uw organisatie.|
|Er is een parner uit de directory verwijderd|Partner uit bedrijf verwijderen.|Er is een partner (gedelegeerde beheerder) uit uw organisatie verwijderd.|
|Bedrijfsgegevens instellen|Bedrijfsgegevens instellen.|De bedrijfsgegevens voor uw organisatie werden bijgewerkt. Dit omvat e-mailadressen voor abonnementsgerelateerde e-mailberichten verzonden door Microsoft 365 en technische meldingen over Microsoft 365-services.|
|Domeinverificatie instellen|Domeinverificatie instellen.|De instelling voor de domeinverificatie voor uw organisatie is gewijzigd.|
|Federatie-instellingen voor een domein zijn bijgewerkt|Federatie-instellingen voor een domein instellen.|De instellingen voor de federatie (extern delen) voor uw organisatie zijn gewijzigd.|
|Wachtwoordbeleid instellen|Wachtwoordbeleid instellen.|De beperkingen voor de lengte en tekens voor gebruikerswachtwoorden in uw organisatie zijn gewijzigd.|
|Microsoft Azure AD-synchronisatie ingeschakeld|DirSyncEnabled-vlag instellen.|De eigenschap waarmee een directory voor Azure AD Sync wordt ingeschakeld, is ingesteld.|
|Domein bijgewerkt|Domein bijwerken.|De instellingen voor een domein in uw organisatie zijn bijgewerkt.|
|Domein geverifieerd|Domein verifiëren.|Er is geverifieerd dat de organisatie de eigenaar is van het domein.|
|Door e-mail geverifieerd domein geverifieerd|Door e-mail geverifieerd domein verifiëren.|E-mailverificatie is gebruikt om te verifiëren dat de organisatie de eigenaar van een domein is.|
||||

### <a name="ediscovery-activities"></a>eDiscovery-activiteiten

Activiteiten in verband met Inhoud zoeken en eDiscovery die worden uitgevoerd in het beveiligings- en compliancecentrum of door de bijbehorende PowerShell-cmdlets uit te voeren, worden geregistreerd in het auditlogboek. Dit omvat de volgende activiteiten:

- Het maken en beheren van eDiscovery-aanvragen

- Het maken, starten en bewerken van zoekopdrachten in inhoud

- Het uitvoeren van acties met betrekking tot Inhoud zoeken, zoals het exporteren, verwijderen en voorbeelden weergeven van zoekresultaten.

- Het configureren van filteren van machtigingen voor Inhoud zoeken

- Het beheren van de beheerrol voor eDiscovery

Zie [eDiscovery-activiteiten zoeken in het auditlogboek](search-for-ediscovery-activities-in-the-audit-log.md) voor een lijst met eDiscovery-activiteiten die worden geregistreerd en een beschrijving ervan.

> [!NOTE]
> Het duurt maximaal 30 minuten voordat gebeurtenissen die het gevolg zijn van de activiteiten die worden weergegeven onder **eDiscovery-activiteiten** en **Geavanceerde eDiscovery-activiteiten** in de vervolgkeuzelijst **Activiteiten** worden weergegeven in de lijst met zoekresultaten. Omgekeerd geldt dat het maximaal 24 uur duurt voor de bijbehorende gebeurtenissen uit eDiscovery-cmdlet-activiteiten worden weergegeven in de lijst met zoekresultaten.

### <a name="advanced-ediscovery-activities"></a>Geavanceerde eDiscovery-activiteiten

U kunt ook in het auditlogboek zoeken naar activiteiten in Geavanceerde eDiscovery. Zie het gedeelte 'Geavanceerde eDiscovery-activiteiten' in [Zoeken naar eDiscovery-activiteiten in het auditlogboek](search-for-ediscovery-activities-in-the-audit-log.md#advanced-ediscovery-activities) voor een beschrijving van deze activiteiten.

### <a name="power-bi-activities"></a>Power BI-activiteiten

U kunt in het auditlogboek zoeken op activiteiten in Power BI. Zie de sectie 'Activiteiten gecontroleerd door Power BI' in [Auditing toepassen in uw organisatie](/power-bi/service-admin-auditing#activities-audited-by-power-bi).

Auditlogboekregistratie voor Power BI is niet standaard ingeschakeld. Om naar Power BI-activiteiten te zoeken in het auditlogboek, moet u de controlefunctie in het beheerportal van Power BI inschakelen. Zie de sectie Auditlogboeken in [Power BI-beheerportal](/power-bi/service-admin-portal#audit-logs).

### <a name="workplace-analytics-activities"></a>Workplace Analytics-activiteiten

Workplace Analytics biedt inzicht in de manier waarop groepen in uw organisatie samenwerken. De volgende tabel bevat activiteiten die zijn uitgevoerd door gebruikers aan welke de beheerdersrol of de analistenrol in Workplace Analytics zijn toegewezen. Gebruikers met de analistenrol hebben volledige toegang tot alle servicefuncties en gebruiken het product voor analyse. Gebruikers met de beheerdersrol kunnen privacyinstellingen en systeeminstellingen configureren en organisatiegegevens voorbereiden, uploaden en controleren in Workplace Analytics. Zie voor meer informatie [Workplace Analytics](/workplace-analytics/index-orig).

|Beschrijvende naam|Bewerking|Omschrijving|
|:-----|:-----|:-----|
|OData-koppeling toegankelijk|AccessedOdataLink|Analyst heeft de OData-koppeling voor een query gebruikt.|
|Geannuleerde query|CanceledQuery|De analist heeft een lopende query geannuleerd.|
|Uitsluiting van vergadering gemaakt|MeetingExclusionCreated|Analyst heeft een uitsluitingsregel voor vergadering gemaakt.|
|Resultaat verwijderd|DeletedResult|De analist heeft een queryresultaat verwijderd.|
|Gedownload rapport|DownloadedReport|Analyst heeft een queryresultaatbestand gedownload.|
|Uitgevoerde query|ExecutedQuery|De analist heeft een query uitgevoerd.|
|Bijgewerkte instelling voor gegevenstoegang|UpdatedDataAccessSetting|Beheerder heeft de instellingen voor gegevenstoegang bijgewerkt.|
|Bijgewerkte privacy-instelling|UpdatedPrivacySetting|Beheerder heeft de privacy-instellingen bijgewerkt, bijvoorbeeld de minimale groepsgrootte.|
|Organisatiegegevens geüpload|UploadedOrgData|De beheerder heeft een organisatiegegevensbestand geüpload.|
|Verkennen bekeken|ViewedExplore|Analisten bekeek visualisaties op een of meer tabbladen op de pagina Verkennen.|
||||

### <a name="microsoft-teams-activities"></a>Activiteiten van Microsoft Teams

U kunt in het auditlogboek zoeken naar activiteiten van gebruikers en beheerders in Microsoft Teams. Teams is een werkruimte met chatfunctie in Office 365. Het brengt de gesprekken, vergaderingen, bestanden en notities van een team samen op één centrale locatie. Zie [Gebeurtenissen zoeken in het auditlogboek in Microsoft Teams](/microsoftteams/audit-log-events#teams-activities) voor beschrijvingen van de Teams-activiteiten die worden gecontroleerd.

### <a name="microsoft-teams-healthcare-activities"></a>Activiteiten in Microsoft Teams Gezondheidszorg

Als in uw organisatie de toepassing [Patiënten](/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-app-overview) in Microsoft Teams wordt gebruikt, kunt u in het auditlogboek zoeken naar activiteiten met betrekking tot het gebruik van de Patiënten-app. Als uw omgeving is geconfigureerd voor de ondersteuning van de app Patiënten, is er een extra activiteitengroep voor deze activiteiten beschikbaar in de keuzelijst **Activiteiten**.

![Microsoft Teams Healthcare-activiteiten in de keuzelijst Activiteiten](../media/TeamsHealthcareAuditActivities.png)

Zie [Auditlogboeken voor de Patiënten-app](/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-audit) voor een beschrijving van de activiteiten van de Patiënten-app.

### <a name="microsoft-teams-shifts-activities"></a>Activiteiten in Microsoft Teams Shifts

Als in uw organisatie de Shifts-app in Microsoft Teams wordt gebruikt, kunt u in het auditlogboek zoeken naar activiteiten met betrekking tot het gebruik van de Shifts-app. Als uw omgeving is geconfigureerd voor de ondersteuning van de Shifts-app, is er een extra activiteitengroep voor deze activiteiten beschikbaar in de keuzelijst **Activiteiten**.

Zie [Gebeurtenissen zoeken in het auditlogboek in Microsoft Teams](/microsoftteams/audit-log-events#shifts-in-teams-activities) voor een beschrijving van de activiteiten van de Shifts-app.

### <a name="yammer-activities"></a>Yammer-activiteiten

In de volgende tabel worden de activiteiten van gebruikers en beheerders in Yammer vermeld die in het auditlogboek zijn vastgelegd. Als u activiteiten in verband met Yammer wilt terughalen uit het auditlogboek, moet u **Resultaten voor alle activiteiten weergeven** selecteren in de lijst **Activiteiten**. Gebruik de datumbereikvakken en de lijst **Gebruikers** om de zoekresultaten te beperken.

|Beschrijvende naam|Bewerking|Beschrijving|
|:-----|:-----|:-----|
|Bewaarbeleid voor gegevens gewijzigd|SoftDeleteSettingsUpdated|Gecontroleerde beheerder wijzigt de instelling voor het bewaarbeleid van netwerkgegevens in Definitieve verwijdering of Voorlopig verwijderen. Alleen gecontroleerde beheerders kunnen deze bewerking uitvoeren.|
|Netwerkconfiguratie gewijzigd|NetworkConfigurationUpdated|Netwerkbeheerder of gecontroleerde beheerder wijzigt de configuratie van het Yammer-netwerk. Hiertoe behoort ook het instellen van het interval voor het exporteren van gegevens en het inschakelen van chatten.|
|Netwerkprofielinstellingen gewijzigd|ProcessProfileFields|Netwerkbeheerder of gecontroleerde beheerder wijzigt de informatie die wordt weergegeven voor de lidprofielen van netwerkgebruikers. |
|Modus voor persoonlijke inhoud gewijzigd|SupervisorAdminToggled|Gecontroleerde beheerder schakelt de *Modus voor persoonlijke inhoud* in of uit. In deze modus kan een beheerder berichten in privégroepen en privéberichten tussen gebruikers (of groepen gebruikers) bekijken. Alleen gecontroleerde beheerders kunnen deze bewerking uitvoeren.|
|Configuratie van beveiliging gewijzigd|NetworkSecurityConfigurationUpdated|Gecontroleerde beheerder wijzigt de configuratie van de beveiliging van het Yammer-netwerk. Hiertoe behoort ook het instellen van verloopbeleid voor het wachtwoord en beperkingen voor IP-adressen. Alleen gecontroleerde beheerders kunnen deze bewerking uitvoeren.|
|Bestand gemaakt|FileCreated|Gebruiker uploadt een bestand.|
|Groep gemaakt|GroupCreation|Gebruiker maakt een groep.|
|Groep verwijderd|GroupDeletion|Er is een groep verwijderd uit Yammer.|
|Bericht verwijderd|MessageDeleted|Gebruiker verwijdert een bericht.|
|Bestand gedownload|FileDownloaded|Gebruiker downloadt een bestand.|
|Gegevens geëxporteerd|DataExport|Gecontroleerde beheerder exporteert gegevens van het Yammer-netwerk. Alleen gecontroleerde beheerders kunnen deze bewerking uitvoeren.|
|Bestand gedeeld|FileShared|Gebruiker deelt een bestand met een andere gebruiker.|
|Netwerkgebruiker geblokkeerd|NetworkUserSuspended|Netwerkbeheerder of gecontroleerd beheerder blokkeert (deactiveert) een gebruiker in Yammer.|
|Gebruiker geblokkeerd|UserSuspension|Gebruikersaccount is geblokkeerd (gedeactiveerd).|
|Beschrijving van bestand gewijzigd|FileUpdateDescription|Gebruiker wijzigt de beschrijving van een bestand.|
|Bestandsnaam bijgewerkt|FileUpdateName|Gebruiker wijzigt de naam van een bestand.|
|Bestand bekeken|FileVisited|Gebruiker bekijkt een bestand.|
||||

### <a name="microsoft-power-automate-activities"></a>Activiteiten in Microsoft Power Automate

U kunt in het auditlogboek zoeken naar activiteiten in Power Automatite (voorheen Microsoft Flow). Deze activiteiten omvatten het maken, bewerken en verwijderen van stromen en het wijzigen van stroommachtigingen. Voor informatie over het controleren van Power Automate-activiteiten, zie de blog  [Controlegebeurtenissen van Microsoft Flow die nu beschikbaar zijn in het Beveiligings- en compliancecentrum](https://flow.microsoft.com/blog/security-and-compliance-center).

### <a name="microsoft-power-apps-activities"></a>Activiteiten in Microsoft Power Apps

U kunt in het auditlogboek zoeken naar app-gerelateerde activiteiten in Power Apps. Deze activiteiten omvatten het maken, starten en publiceren van een app. Het toewijzen van machtigingen aan apps wordt ook gecontroleerd. Zie voor een beschrijving van alle activiteiten in Power Apps [Activiteitenregistratie voor Power Apps](/power-platform/admin/logging-powerapps#what-events-are-audited).

### <a name="microsoft-stream-activities"></a>Activiteiten in Microsoft Stream

U kunt in het auditlogboek zoeken op activiteiten in Microsoft Stream. Voorbeelden van deze activiteiten zijn videoactiviteiten uitgevoerd door gebruikers, groepsactiviteiten via een kanaal en beheeractiviteiten, zoals het beheren van gebruikers, het beheren van organisatie-instellingen en het exporteren van rapporten. Zie de sectie 'Acties geregistreerd in Stream' in [Auditlogboeken in Microsoft Stream](/stream/audit-logs#actions-logged-in-stream) voor een beschrijving van deze activiteiten.

### <a name="content-explorer-activities"></a>Activiteiten in inhoudsverkenner

De volgende tabel geeft een overzicht van de activiteiten in de inhoudsverkenner die zijn vastgelegd in het auditlogboek. Inhoudsverkenner, dat wordt weergegeven in het hulpprogramma Gegevensclassificaties in het Microsoft 365-compliancecentrum. Zie voor meer informatie [Gegevensclassificatie inhoudsverkenner gebruiken](data-classification-content-explorer.md).

|Beschrijvende naam|Bewerking|Omschrijving|
|:-----|:-----|:-----|
|Bestand geopend|LabelContentExplorerAccessedItem|Een beheerder (of een gebruiker die lid is van de rollengroep Inhoudsviewer voor Inhoudsverkenner) gebruikt inhoudsverkenner om een e-mailbericht of SharePoint/OneDrive-document te bekijken.|
||||

### <a name="quarantine-activities"></a>Activiteiten in quarantaine

De volgende tabel bevat de quarantaineactiviteiten die u kunt zoeken in het auditlogboek. Zie voor meer informatie over quarantaine [Berichten in quarantaine plaatsen in Office 365](../security/office-365-security/quarantine-email-messages.md).

|Beschrijvende naam|Bewerking|Omschrijving|
|:-----|:-----|:-----|
|Bericht over verwijderde quarantaine|QuarantineDelete|Een gebruiker heeft een e-mailbericht verwijderd dat schadelijk zou zijn.|
|Bericht over geëxporteerde quarantaine|QuarantineExport|Een gebruiker heeft een e-mailbericht geëxporteerd dat schadelijk zou zijn.|
|Bericht over voorbeeld van quarantaine|QuarantinePreview|Een gebruiker heeft een e-mailbericht bekeken dat schadelijk zou zijn.|
|Bericht dat uit quarantaine is gehaald|QuarantineRelease|Een gebruiker heeft een e-mailbericht uit quarantaine gehaald dat schadelijk zou zijn.|
|Koptekst van bekeken quarantainebericht|QuarantineViewHeader|Een gebruiker heeft de koptekst bekeken van een e-mailbericht dat schadelijk zou zijn.|
||||

### <a name="microsoft-forms-activities"></a>Activiteiten in Microsoft Forms

In de volgende tabel worden de activiteiten van gebruikers en beheerders in Microsoft Forms vermeld die in het auditlogboek zijn vastgelegd. Microsoft Forms is een hulpmiddel voor formulieren/toets/enquête waarmee gegevens worden verzameld voor analyse. 

Zoals hieronder wordt vermeld in de beschrijvingen, bevatten sommige bewerkingen aanvullende activiteitsparameters.

> [!NOTE]
> Als een Formulieractiviteit wordt uitgevoerd door een medeauteur of anonieme gebruiker, wordt deze iets anders geregistreerd. Zie voor meer informatie de sectie [Formulieractiviteiten die zijn uitgevoerd door co-auteurs en anonieme gebruikers](#forms-activities-performed-by-coauthors-and-anonymous-responders).

|Beschrijvende naam|Bewerking|Omschrijving|
|:-----|:-----|:-----|
|Opmerking gemaakt|CreateComment|De eigenaar van het formulier voegt een opmerking of score toe aan een toets.|
|Formulier gemaakt|CreateForm|De eigenaar van het formulier maakt een nieuw formulier.|
|Formulier bewerkt|EditForm|De eigenaar van het formulier bewerkt een formulier, zoals een vraag maken, verwijderen of bewerken. De eigenschap *EditOperation:string* geeft de naam van de bewerking aan. Mogelijke waarden zijn:<br/>- CreateQuestion<br/>- CreateQuestionChoice <br/>- DeleteQuestion <br/>- DeleteQuestionChoice <br/>- DeleteFormImage <br/>- DeleteQuestionImage <br/>- UpdateQuestion <br/>- UpdateQuestionChoice <br/>- UploadFormImage/Bing/Onedrive <br/>- UploadQuestionImage <br/>- ChangeTheme <br><br>FormImage bevat elke plaats in Formulieren waar gebruikers een afbeelding kunnen uploaden, bijvoorbeeld in een query of als achtergrondthema.|
|Verplaatst formulier|MoveForm|De eigenaar van het formulier verplaatst een formulier. <br><br>Eigenschap DestinationUserId:string geeft de gebruikers-id aan van de persoon die het formulier heeft verplaatst. Eigenschap NewFormId:string is de nieuwe id voor het zojuist gekopieerde formulier.|
|Verwijderd formulier|DeleteForm|De formuliereigenaar verwijdert een formulier. Dit geldt ook voor SoftDelete (verwijderoptie en formulier verplaatst naar Prullenbak) en HardDelete (Prullenbak wordt geleegd).|
|Bekeken formulier (ontwerptijd)|ViewForm|Formuliereigenaar opent een bestaand formulier om te bewerken.|
|Voorbeeld van formulier bekeken|PreviewForm|De eigenaar van het formulier bekijkt een voorbeeld van een formulier met de functie Voorbeeld.|
|Geëxporteerd formulier|ExportForm|Formuliereigenaar exporteert resultaten naar Excel. <br><br>Eigenschap ExporterenOpmaak:string geeft aan of het Excel-bestand een Download of Online is.|
|Toegestaan formulier delen voor kopie|AllowShareFormForCopy|De eigenaar van het formulier maakt een sjabloonkoppeling om het formulier met andere gebruikers te delen. Deze gebeurtenis wordt geregistreerd wanneer de eigenaar van het formulier klikt om de sjabloon-URL te genereren.|
|Formulier delen voor kopie niet toegestaan|DisallowShareFormForCopy|Formuliereigenaar verwijdert sjabloonkoppeling.|
|Formulier co-auteur toegevoegd|AddFormCoauthor|Een gebruiker gebruikt een koppeling voor samenwerking om antwoorden te ontwerpen/weer te geven. Deze gebeurtenis wordt geregistreerd wanneer een gebruiker een samenwerkings-URL gebruikt (niet wanneer de samenwerkings-URL voor het eerst wordt gegenereerd).|
|Formulier co-auteur verwijderd|RemoveFormCoauthor|Formuliereigenaar verwijdert een samenwerkingskoppeling.|
|Pagina Bekeken antwoord|ViewRuntimeForm|Gebruiker heeft een antwoordpagina geopend om weer te geven. Deze gebeurtenis wordt geregistreerd, ongeacht of de gebruiker een antwoord indient.|
|Antwoord gemaakt|CreateResponse|Net als het ontvangen van een nieuw antwoord.  Een gebruiker heeft een antwoord op een formulier ingediend. <br><br>Eigenschap ResponseId:string en eigenschap ResponderId:string geeft aan welk resultaat wordt bekeken. <br><br>Voor een anonieme responder is de eigenschap ResponderId null.|
|Bijgewerkt antwoord|UpdateResponse|De eigenaar van het formulier heeft een opmerking of score voor een toets bijgewerkt. <br><br>Eigenschap ResponseId:string en eigenschap ResponderId:string geeft aan welk resultaat wordt bekeken. <br><br>Voor een anonieme responder is de eigenschap ResponderId null.|
|Alle antwoorden verwijderd|DeleteAllResponses|Formuliereigenaar verwijdert alle antwoordgegevens.|
|Verwijderd antwoord|DeleteResponse|Formuliereigenaar verwijdert één antwoord. <br><br>Eigenschap ResponseId:string geeft het antwoord aan dat wordt verwijderd.|
|Bekeken antwoorden|ViewResponses|De eigenaar van het formulier bekijkt de samengevoegde lijst met antwoorden. <br><br>Eigenschap ViewType:string geeft aan of de eigenaar van het formulier Details of Aggregaat bekijkt|
|Bekeken antwoord|ViewResponse|De eigenaar van het formulier bekijkt een bepaald antwoord. <br><br>Eigenschap ResponseId:string en eigenschap ResponderId:string geeft aan welk resultaat wordt bekeken. <br><br>Voor een anonieme responder is de eigenschap ResponderId null.|
|Koppeling gemaakt overzicht|GetSummaryLink|De eigenaar van het formulier maakt een koppeling naar samenvattingsresultaten om resultaten te delen.|
|Koppeling verwijderde samenvatting|DeleteSummaryLink|De eigenaar van het formulier verwijdert de koppeling met samenvattingsresultaten.|
|Bijgewerkt formulier phishing-status|UpdatePhishingStatus|Deze gebeurtenis wordt geregistreerd wanneer de gedetailleerde waarde voor de interne beveiligingsstatus is gewijzigd, ongeacht of dit de uiteindelijke beveiligingsstatus heeft gewijzigd (het formulier is nu bijvoorbeeld Gesloten of Geopend). Dit betekent dat er mogelijk dubbele gebeurtenissen worden aangemaakt zonder dat de uiteindelijke beveiligingstoestand wordt gewijzigd. De mogelijke statuswaarden voor deze gebeurtenis zijn:<br/>- Take Down <br/>- Take Down by Admin <br/>- Admin Unblocked <br/>- Auto Blocked <br/>- Auto Unblocked <br/>- Customer Reported <br/>- Reset Customer Reported|
|Bijgewerkte gebruiker phishing-status|UpdateUserPhishingStatus|Deze gebeurtenis wordt geregistreerd wanneer de waarde voor de beveiligingsstatus van de gebruiker is gewijzigd. De waarde van de gebruikersstatus in de auditrecord is **Bevestigd als Phisher** toen de gebruiker een phishingformulier maakte dat is ingenomen door het veiligheidsteam van Microsoft Online. Als een beheerder de blokkering van de gebruiker opheft, wordt de waarde van de status van de gebruiker ingesteld op **Opnieuw instellen als normale gebruiker**.|
|Uitnodiging Verzonden Pro-formulieren|ProInvitation|Gebruiker klikt om een proefversie van Pro te activeren.|
|Bijgewerkte formulierinstelling|UpdateFormSetting|De eigenaar van het formulier werkt een formulierinstelling bij. <br><br>Eigenschap FormSettingName:string geeft de naam en nieuwe waarde van de instelling aan.|
|Gebruikersinstelling bijgewerkt|UpdateUserSetting|De eigenaar van het formulier werkt een gebruikersinstelling bij. <br><br>Eigenschap UserSettingName:string geeft de naam en nieuwe waarde van de instelling aan.|
|Weergegeven formulieren|ListForms|De eigenaar van het formulier bekijkt een lijst met formulieren. <br><br>Eigenschap ViewType:string geeft aan in welke weergave de eigenaar van het formulier kijkt: Alle formulieren, Gedeeld met mij of Groepsformulieren|
|Verzonden antwoord|SubmitResponse|Een gebruiker heeft een antwoord op een formulier ingediend. <br><br>Met Eigenschap IsInternalForm:boolean wordt aangegeven of de persoon binnen dezelfde organisatie valt als de eigenaar van het formulier.|
||||

#### <a name="forms-activities-performed-by-coauthors-and-anonymous-responders"></a>Formulieractiviteiten die zijn uitgevoerd door medeauteurs en anonieme beantwoorders

Formulieren ondersteunen samenwerking bij het ontwerpen en analyseren van antwoorden. Een samenwerker voor een formulier wordt een *medeauteur* genoemd. Medeauteurs kunnen alles doen wat een eigenaar van een formulier kan doen, behalve een formulier verwijderen of verplaatsen. Met formulieren kunt u ook een formulier maken waarop anoniem kan worden gereageerd. Dit betekent dat de beantwoorder niet hoeft te zijn aangemeld bij uw organisatie om te reageren op een formulier.

In de volgende tabel worden de controleactiviteiten en informatie in de auditrecord beschreven voor activiteiten die zijn uitgevoerd door coauteurs en anonieme beantwoorders.

|Activiteitstype|Interne of externe gebruiker|Gebruikers-id die wordt geregistreerd|Organisatie waarbij is aangemeld|Gebruikerstype Formulieren|
|:-----|:-----|:-----|:-----|:-----|
|Medeauteursactiviteiten|Intern|UPN|De organisatie van de eigenaar van het formulier|Medeauteur|
|Medeauteursactiviteiten|Extern|UPN<br>|Organisatie van de medeauteur<br>|Medeauteur|
|Medeauteursactiviteiten|Extern|`urn:forms:coauthor#a0b1c2d3@forms.office.com`<br>(Het tweede deel van de id is een hash, die voor verschillende gebruikers verschillend is)|De organisatie van de eigenaar van het formulier<br>|Medeauteur|
|Antwoordactiviteiten|Extern|UPN<br>|Organisatie van beantwoorder<br>|Beantwoorder|
|Antwoordactiviteiten|Extern|`urn:forms:external#a0b1c2d3@forms.office.com`<br>(Het tweede deel van de gebruikers-id is een hash, die verschilt per gebruiker)|De organisatie van de eigenaar van het formulier|Beantwoorder|
|Antwoordactiviteiten|Anoniem|`urn:forms:anonymous#a0b1c2d3@forms.office.com`<br>(Het tweede deel van de gebruikers-id is een hash, die verschilt per gebruiker)|De organisatie van de eigenaar van het formulier|Beantwoorder|
||||

### <a name="sensitivity-label-activities"></a>Activiteiten voor gevoeligheidslabels

De volgende tabel bevat gebeurtenissen die het gevolg zijn van labelactiviteiten voor SharePoint Online- en Teams-sites.

|Beschrijvende naam|Bewerking|Omschrijving|
|:-----|:-----|:-----|
|Toegepaste gevoeligheidslabel op site|SensitivityLabelApplied|Er is een gevoeligheidslabel toegepast op een SharePoint- of Teams-site.|
|Gevoeligheidslabel verwijderd van site|SensitivityLabelRemoved|Een gevoeligheidslabel is verwijderd van een SharePoint- of Teams-site.|
|Toegepaste gevoeligheidslabel op bestand|FileSensitivityLabelApplied|Een gevoeligheidslabel is toegepast op een document met behulp van Office op het web of een beleid voor automatisch labelen.|
|Gewijzigde gevoeligheidslabel toegepast op bestand|FileSensitivityLabelChanged|Een ander gevoeligheidslabel is toegepast op een document met behulp van Office op het web of een beleid voor automatisch labelen.|
|Gevoeligheidslabel verwijderd van bestand|FileSensitivityLabelRemoved|Een gevoeligheidslabel is verwijderd uit een document met behulp van de web-app van Office, een beleid voor automatisch labelen of met behulp van de cmdlet [Unlock-SPOSensitivityLabelEncrypteFile](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile).|
||||

### <a name="retention-policy-and-retention-label-activities"></a>Activiteiten met bewaarbeleid en bewaarlabels

|Beschrijvende naam|Bewerking|Omschrijving|
|:-----|:-----|:-----|
| Geconfigureerde instellingen voor een bewaarbeleid |NewRetentionComplianceRule |De beheerder heeft de instellingen voor bewaren geconfigureerd voor een nieuw bewaarbeleid. Bewaarinstellingen omvatten de periode waarin items worden bewaard en wat er met items gebeurt wanneer de bewaarperiode is verstreken (zoals items verwijderen, items bewaren of bewaren en vervolgens verwijderen). Deze activiteit komt ook overeen met het uitvoeren van de cmdlet [New-RetentionComplianceRule](/powershell/module/exchange/new-retentioncompliancerule).|
| Bewaarlabel gemaakt |NewComplianceTag |Beheerder heeft een nieuw bewaarlabel gemaakt.|
| Bewaarbeleid gemaakt |NewRetentionCompliancePolicy|Beheerder heeft een nieuw bewaarbeleid gemaakt.|
| Instellingen uit een bewaarbeleid verwijderd| RemoveRetentionComplianceRule<br/>| Beheerder heeft de configuratie-instellingen van een bewaarbeleid verwijderd. Deze activiteit wordt waarschijnlijk geregistreerd wanneer een beheerder een bewaarbeleid verwijdert of de cmdlet [Remove-RetentionComplianceRule](/powershell/module/exchange/Remove-RetentionComplianceRule) uitvoert.|
| Label bewaarbeleid verwijderd |RemoveComplianceTag | Beheerder heeft een bewaarlabel verwijderd.|
| Bewaarbeleid verwijderd |RemoveRetentionCompliancePolicy<br/> |Beheerder heeft een bewaarbeleid verwijderd. |
| Optie voor het bewaren van labels voor bewaarbeleid ingeschakeld<br/> |SetRestrictiveRetentionUI |De beheerder heeft de cmdlet [Set-RegulatoryComplianceUI](/powershell/module/exchange/set-regulatorycomplianceui) uitgevoerd, zodat een beheerder vervolgens de UI-configuratieoptie voor een bewaarlabel kan selecteren om inhoud als een record van regelgeving te markeren.|
| Bijgewerkte instellingen voor een bewaarbeleid | SetRetentionComplianceRule | De beheerder heeft de instellingen voor het bewaren van een bestaand bewaarbeleid gewijzigd. Bewaarinstellingen omvatten de periode waarin items worden bewaard en wat er met items gebeurt wanneer de bewaarperiode is verstreken (zoals items verwijderen, items bewaren of bewaren en vervolgens verwijderen). Deze activiteit komt ook overeen met het uitvoeren van de cmdlet [Set-RetentionComplianceRule](/powershell/module/exchange/set-retentioncompliancerule). |
| Bewaarlabel bijgewerkt |SetComplianceTag  | Beheerder heeft een bestaand bewaarlabel bijgewerkt.|
| Bewaarbeleid bijgewerkt |SetRetentionCompliancePolicy |Beheerder werkt een bestaand bewaarbeleid bij. Updates die deze gebeurtenis activeren, zijn onder andere het toevoegen of uitsluiten van inhoudslocaties waar het bewaarbeleid op wordt toegepast.|
||||

### <a name="briefing-email-activities"></a>Briefing-e-mailactiviteiten

De volgende tabel geeft een overzicht van de activiteiten in Briefing-e-mail die zijn vastgelegd in het Office 365-controlelogboek. Voor meer informatie over Briefing-e-mail, zie:

- [Overzicht van Briefing-e-mail](/Briefing/be-overview)

- [Briefing-e-mail configureren](/Briefing/be-admin)

|**Beschrijvende naam**|**Bewerking**|**Beschrijving**|
|:-----|:-----|:-----|
|Bijgewerkte privacyinstellingen van organisatie|UpdatedOrganizationBriefingSettings|Beheerder werkt de privacyinstellingen van de organisatie bij voor briefing-e-mail. |
|Bijgewerkte privacyinstellingen voor gebruikers|UpdatedUserBriefingSettings|Beheerder werkt de privacyinstellingen van de gebruiker voor briefing-e-mail bij.
||||

### <a name="myanalytics-activities"></a>Activiteiten in MyAnalytics

De volgende tabel geeft een overzicht van de activiteiten in MyAnalytics die zijn vastgelegd in het Office 365-controlelogboek. Zie voor meer informatie over MyAnalytics, [MyAnalytics voor beheerders](/workplace-analytics/myanalytics/overview/mya-for-admins).

|**Beschrijvende naam**|**Bewerking**|**Beschrijving**|
|:-----|:-----|:-----|
|Bijgewerkte instellingen van MyAnalytics van de organisatie|UpdatedOrganizationMyAnalyticsSettings|Beheerder werkt instellingen op organisatieniveau bij voor MyAnalytics. |
|Bijgewerkte instellingen van de gebruiker voor MyAnalytics|UpdatedUserMyAnalyticsSettings|Beheerder werkt gebruikersinstellingen voor MyAnalytics bij.|
||||

### <a name="information-barriers-activities"></a>Activiteiten in informatiebelemmeringen

De volgende tabel geeft een overzicht van de activiteiten in informatiebelemmeringen die zijn vastgelegd in het Office 365-controlelogboek. Zie voor meer informatie over informatiebelemmeringen [Meer informatie over informatiebelemmeringen in Microsoft 365](information-barriers.md).

|**Beschrijvende naam**|**Bewerking**|**Beschrijving**|
|:----------------|:------------|:--------------|
| Segmenten aan een site toegevoegd | Segmentengeadd | Een SharePoint-beheerder, globale beheerder of site-eigenaar heeft segmenten van een of meer informatiesegmenten aan een site toegevoegd. |
| Segmenten van een site gewijzigd | SegmentsChanged | Een SharePoint- of globale beheerder heeft een of meer segmenten met informatiebelemmeringen voor een site gewijzigd. |
| Segmenten van een site verwijderd | Segmentenremoved | Een SharePoint- of globale beheerder heeft een of meer segmenten met informatiebelemmeringen van een site verwijderd. |
||||

### <a name="exchange-admin-audit-log"></a>Auditlogboek voor Exchange-beheerders

Controlelogboekregistratie voor Exchange-beheerders (die standaard is ingeschakeld in Office 365) registreert een gebeurtenis in het auditlogboek wanneer een beheerder (of een gebruiker aan wie beheerdersmachtigingen zijn toegewezen) een wijziging aanbrengt in uw Exchange Online-organisatie. Wijzigingen die zijn aangebracht via het Exchange-beheercentrum of door een cmdlet uit te voeren in Exchange Online PowerShell, worden geregistreerd in het auditlogboek voor Exchange-beheerders. Cmdlets die beginnen met de werkwoorden **Get-**, **Search-** of **Test-** worden niet geregistreerd in het auditlogboek. Zie voor meer informatie over auditlogregistratie voor beheerders in Exchange [Controlelogboekregistratie voor beheerders](/exchange/administrator-audit-logging-exchange-2013-help).

> [!IMPORTANT]
> Sommige Exchange Online-cmdlets die niet zijn geregistreerd in het auditlogboek voor Exchange-beheerders (of in het auditlogboek). Veel van deze cmdlets zijn gerelateerd aan het onderhouden van de Exchange Online-service en worden uitgevoerd door personeel of serviceaccounts van het Microsoft-datacenter. Deze cmdlets worden niet geregistreerd, omdat ze zouden leiden tot een groot aantal 'lange' controlegebeurtenissen. Als er een Exchange Online-cmdlet is die niet wordt gecontroleerd, kunt u een suggestie indienen op het [Security & Compliance User Voice-forum](https://office365.uservoice.com/forums/289138-office-365-security-compliance) en vragen of deze kan worden ingeschakeld voor controle. U kunt ook een aanvraag voor een ontwerpwijziging (DCR) indienen bij Microsoft-ondersteuning.

Hier zijn enkele tips voor het zoeken naar activiteiten van Exchange-beheerders bij het zoeken in het auditlogboek:

- Als u vermeldingen wilt retourneren uit het auditlogboek voor Exchange-beheerders, moet u **Resultaten tonen voor alle activiteiten** in de lijst **Activiteiten** selecteren. Gebruik de datumbereikvakken en de lijst **Gebruikers** om de zoekresultaten te beperken voor cmdlets die worden uitgevoerd door een specifieke Exchange-beheerder binnen een bepaald datumbereik.

- Als u gebeurtenissen uit het auditlogboek van de Exchange-beheerder wilt weergeven, filtert u de zoekresultaten en typt u een **-** (streepje) in het filtervak **Activiteit**. Hierdoor worden de namen van de cmdlets weergegeven in de kolom **Activiteit** voor gebeurtenissen van Exchange-beheerders. U kunt vervolgens de namen van de cmdlets op alfabetische volgorde sorteren.

  ![Typ een streepje in het vak Activiteiten om Exchange-beheergebeurtenissen te filteren](../media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)

- Als u informatie wilt hebben over welke cmdlet is uitgevoerd, welke parameters en parameterwaarden zijn gebruikt en welke objecten zijn beïnvloed, dan kunt u de zoekresultaten exporteren en de optie **Alle resultaten downloaden** selecteren. Zie voor meer informatie [Auditlogboekrecords exporteren, configureren en weergeven](export-view-audit-log-records.md).

- U kunt ook de opdracht `Search-UnifiedAuditLog -RecordType ExchangeAdmin` in Exchange Online PowerShell gebruiken om alleen controlerecords uit het auditlogboek van de Exchange-beheerder te retourneren. Nadat een Exchange-cmdlet is uitgevoerd, kan het tot 30 minuten duren voordat de bijbehorende auditlogboekinvoer in de zoekresultaten wordt geretourneerd. Zie [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) voor meer informatie. Voor informatie over het exporteren van de zoekresultaten die zijn geretourneerd door de **Search-UnifiedAuditLog**-cmdlet naar een CSV-bestand, zie de sectie 'Tips voor het exporteren en bekijken van het auditlogboek' in [Auditlogboekrecords exporteren, configureren en weergeven](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log).

- U kunt gebeurtenissen in het auditlogboek van Exchange-beheerders ook bekijken via het Exchange-beheercentrum of door de **Search-AdminAuditLog-** in Exchange Online PowerShell uit te voeren. Dit is een goede manier om specifiek te zoeken naar activiteiten die zijn uitgevoerd door beheerders van Exchange Online. Zie voor instructies:

  - [Het auditlogboek voor beheerders bekijken](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)

  - [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog)

   Houd er rekening mee dat dezelfde activiteiten van Exchange-beheerders worden geregistreerd in het auditlogboek voor Exchange-beheerders en in het auditlogboek.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

**Wat zijn de verschillende Microsoft 365-services die momenteel worden gecontroleerd?**

De meest gebruikte services, zoals Exchange Online, SharePoint Online, OneDrive voor Bedrijven, Azure Active Directory, Microsoft Teams, Dynamics 365, Defender voor Office 365 en Power BI, worden gecontroleerd. Zie het [begin van dit artikel](search-the-audit-log-in-security-and-compliance.md) voor een lijst met services die worden gecontroleerd.

**Welke activiteiten worden gecontroleerd door de controleservice in Office 365?**

Zie de [Gecontroleerde activiteiten](#audited-activities) in dit artikel voor een lijst en een beschrijving van de activiteiten die worden gecontroleerd.

**Hoe lang duurt het voordat een controlerecord beschikbaar is nadat een gebeurtenis is opgetreden?**

De meeste controlegegevens zijn binnen 30 minuten beschikbaar, maar het kan tot 24 uur duren voordat de bijbehorende auditlogboekinvoer in de zoekresultaten wordt weergegeven. Zie de tabel in de sectie [Vereisten voor het doorzoeken van het auditlogboek](#requirements-to-search-the-audit-log) van dit artikel waarin wordt beschreven hoe lang het duurt voordat gebeurtenissen in de verschillende services beschikbaar zijn.

**Hoe lang worden de controlerecords bewaard?**

Zoals eerder uitgelegd, worden controlerecords voor activiteiten die zijn uitgevoerd door gebruikers met een Office 365 E5- of Microsoft E5-licentie (of gebruikers met een invoeglicentie voor Microsoft 365 E5) voor één jaar bewaard. Voor alle andere abonnementen die geïntegreerde controlelogregistratie ondersteunen, worden controlerecords 90 dagen bewaard.

**Heb ik via een programma toegang tot de controlegegevens?**

Ja. De Office 365 Management Activity-API wordt gebruikt om de auditlogboeken via een programma op te halen.  Zie voor meer informatie [Aan de slag met Beheer-API's van Office 365](/office/office-365-management-api/get-started-with-office-365-management-apis).

**Zijn er andere manieren om controlelogboeken te vinden, anders dan met behulp van het beveiligings- en compliancecentrum of de Office 365 Management Activity-API?**

Nee. Dit zijn de enige twee manieren om gegevens op te halen uit de controleservice.

**Moet ik de controle individueel inschakelen voor elke service waar ik auditlogboeken voor wil vastleggen?**

In de meeste services is controle standaard ingeschakeld nadat u in eerste instantie de controle voor uw organisatie hebt ingeschakeld (zoals wordt beschreven in de sectie [Vereisten voor het doorzoeken van het auditlogboek](#requirements-to-search-the-audit-log) in dit artikel).

**Biedt de controleservice ondersteuning voor ontdubbelen van records?**

Nee. De auditservicepijplijn is in realtime en kan daarom geen ondersteuning bieden voor duplicatie.

**Wordt de gegevensstroom in verschillende regio's gecontroleerd?**

Nee. Er zijn momenteel controleimplementaties voor pijplijnen in de regio's NA (Noord-Amerika), EMEA (Europa, het Midden-Oosten en Afrika) en APAC (Azië en Stille Oceaan). Het is echter mogelijk dat de gegevens alleen tijdens problemen met de livesite over deze gebieden worden verdeeld voor taakverdeling. Wanneer we deze activiteiten uitvoeren, worden de gegevens die worden verzonden versleuteld.

**Zijn controlegegevens versleuteld?**

Controlegegevens worden opgeslagen in Exchange-postvakken (in opgeslagen gegevens) in dezelfde regio waar de geïntegreerde controlepijplijn is geïmplementeerd. Postvakgegevens die worden opgeslagen, worden niet versleuteld door Exchange. Met versleuteling op serviceniveau worden echter alle postvakgegevens versleuteld, omdat Exchange-servers in Microsoft-datacenters zijn versleuteld via BitLocker. Zie voor meer informatie [Office 365-versleuteling voor Skype voor Bedrijven, OneDrive voor Bedrijven, SharePoint Online en Exchange Online](/compliance/assurance/assurance-encryption-for-microsoft-365-services).

E-mailgegevens die onderweg zijn, worden altijd versleuteld.
