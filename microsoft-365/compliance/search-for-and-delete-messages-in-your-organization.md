---
title: E-mailberichten in uw organisatie zoeken en verwijderen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Gebruik de functie Zoeken en verwijderen in het Microsoft 365-compliancecentrum om een e-mailbericht te zoeken en te verwijderen uit alle postvakken in uw organisatie.
ms.openlocfilehash: 95683ed5dc6cce8ff109976ebb0d13215593f046
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770707"
---
# <a name="search-for-and-delete-email-messages"></a>E-mailberichten zoeken en verwijderen

**Dit artikel is bedoeld voor beheerders. Probeert u items in uw postvak te vinden die u wilt verwijderen? Raadpleeg dan [Een bericht of item zoeken met Direct zoeken](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**.

U kunt de functie Zoeken en verwijderen gebruiken om een e-mailbericht te zoeken en te verwijderen uit alle postvakken in uw organisatie. Dit kan u helpen om mogelijk schadelijke e-mailberichten of e-mailberichten met een hoog risico te zoeken en verwijderen, zoals:

- Berichten die schadelijke bijlagen of virussen bevatten

- Phishingberichten

- Berichten die gevoelige gegevens bevatten

> [!CAUTION]
> Zoeken en verwijderen is een krachtige functie waarmee iedereen aan wie de benodigde machtigingen is toegewezen e-mailberichten kan verwijderen uit postvakken in uw organisatie.

## <a name="before-you-begin"></a>Voordat u begint

- Om Inhoud zoeken te maken en uit te voeren, moet u lid zijn van de rollengroep **eDiscovery-manager** of aan de rol **Compliance zoeken** in Beveiligings- en compliancecentrum zijn toegewezen. Om berichten te verwijderen, moet u lid zijn van de rollengroep **Organisatiebeheer** of aan de rol **Zoeken en opschonen** in het Beveiligings- en compliancecentrum zijn toegewezen. Zie [eDiscovery-machtigingen toewijzen in het Beveiligings- en compliancecentrum](assign-ediscovery-permissions.md) voor informatie over het toevoegen van gebruikers aan een rollengroep.

  > [!NOTE]
  > De rollengroep **Organisatiebeheer** bestaat zowel in Exchange Online als in het Beveiligings- en compliancecentrum. Dit zijn afzonderlijke rollengroepen die verschillende machtigingen geven. Als lid van **Organisatiebeheer** in Exchange Online worden de vereiste machtigingen voor het verwijderen van e-mailberichten niet verleend. Als u niet de rol **Zoeken en opschonen** toegewezen hebt gekregen in Beveiligings- en compliancecentrum (rechtstreeks of via een rollengroep zoals **Organisatiebeheer**), wordt u in stap 3 een fout weergegeven wanneer u de cmdlet **New-ComplianceSearchAction** uitvoert met het bericht 'Er kan geen parameter worden gevonden die overeenkomt met de parameternaam 'Opschonen'.

- U moet PowerShell voor het beveiligings- en compliancecentrum gebruiken om berichten te verwijderen. Zie [stap 1](#step-1-connect-to-security--compliance-center-powershell) voor instructies over het maken van verbinding.

- U kunt per keer maximaal 10 items per postvak verwijderen. Omdat de mogelijkheid om berichten te zoeken en te verwijderen is bedoeld als een hulpprogramma voor incidentele reactie, zorgt deze limiet ervoor dat berichten snel uit postvakken worden verwijderd. Deze functie is niet bedoeld om postvakken van gebruikers op te schonen.

- Het maximum aantal postvakken in een inhoudszoekactie dat u kunt gebruiken om items te verwijderen via een zoek- en opschoningsopdracht is 50.000. Als met de zoekopdracht (die u in [stap 2](#step-2-create-a-content-search-to-find-the-message-to-delete) maakt) in meer dan 50.000 postvakken wordt gezocht, mislukt de opschoningsactie (die u in stap 3 maakt). Er kan meestal worden gezocht naar meer dan 50.000 postvakken in één zoekopdracht wanneer u de zoekopdracht zo configureert dat alle postvakken in uw organisatie worden gebruikt. Deze beperking geldt ook wanneer minder dan 50.000 postvakken items bevatten die overeenkomen met de zoekopdracht. Zie de sectie [Meer informatie](#more-information) voor instructies voor het gebruik van zoekmachtigingsfilters voor het zoeken naar en verwijderen van items uit meer dan 50.000 postvakken.

- De procedure in dit artikel kan alleen worden gebruikt om items in postvakken en openbare mappen van Exchange Online te verwijderen. U kunt deze niet gebruiken om inhoud te verwijderen van SharePoint- of OneDrive voor Bedrijven-sites.

- E-mailitems in een revisieset in een Advanced eDiscovery-zaak kunnen niet worden verwijderd met behulp van de procedures in dit artikel. Items in een revisieset zijn namelijk opgeslagen in een Azure-opslaglocatie en niet in de liveservice. Dit betekent dat deze niet worden geretourneerd door de inhoudszoekactie die u in stap 1 hebt gemaakt. Als u items in een revisieset wilt verwijderen, moet u de Advanced eDiscovery-zaak met de revisieset verwijderen. Zie [Advanced eDiscovery-zaak sluiten of verwijderen](close-or-delete-case.md) voor meer informatie.

## <a name="step-1-connect-to-security--compliance-center-powershell"></a>Stap 1: verbinding maken met Beveiligings- en compliancecentrum van PowerShell

De eerste stap is het maken van verbinding met Beveiligings- en compliancecentrum van PowerShell voor uw organisatie. Zie [Verbinding maken met Beveiligings- en compliancecentrum van Powershell](/powershell/exchange/connect-to-scc-powershell) voor stapsgewijze instructies.

## <a name="step-2-create-a-content-search-to-find-the-message-to-delete"></a>Stap 2: een inhoudszoekactie maken om het te verwijderen bericht te zoeken

De tweede stap bestaat uit het maken en uitvoeren van een Inhoudszoekactie om het bericht te zoeken dat u wilt verwijderen uit postvakken in uw organisatie. U kunt de zoekopdracht maken met behulp van het Microsoft 365-compliancecentrum of door de cmdlets **New-ComplianceSearch** en **Start-ComplianceSearch** in Beveiligings- en compliancecentrum van PowerShell uit te voeren. De berichten die overeenkomen met de query voor deze zoekopdracht worden verwijderd door de opdracht **New-ComplianceSearchAction -Purge** in [Stap 3](#step-3-delete-the-message) uit te voeren. Zie de volgende onderwerpen voor informatie over het maken van een Inhoudszoekopdracht en het configureren van zoekquery's:

- [Inhoud zoeken in Office 365 ](content-search.md)

- [Trefwoordquery's voor Inhoud zoeken](keyword-queries-and-search-conditions.md)

- [New-ComplianceSearch](/powershell/module/exchange/New-ComplianceSearch)

- [Start-ComplianceSearch](/powershell/module/exchange/Start-ComplianceSearch)

> [!NOTE]
> De inhoudslocaties waarin wordt gezocht in de Inhoudszoekopdracht die u in deze stap maakt, kunnen geen SharePoint- of OneDrive voor Bedrijven-sites bevatten. U kunt alleen postvakken en openbare mappen opnemen in een Inhoudszoekopdracht die wordt gebruikt voor e-mailberichten. Als de Inhoudszoekopdracht sites bevat, krijgt u een foutmelding in Stap 3 wanneer u de cmdlet **New-ComplianceSearchAction** uitvoert.

### <a name="tips-for-finding-messages-to-remove"></a>Tips voor het zoeken naar berichten die u wilt verwijderen

Het doel van de zoekopdracht is om de resultaten van de zoekopdracht te beperken tot alleen het bericht of de berichten die u wilt verwijderen. Hier zijn enkele tips:

- Gebruik de eigenschap **Onderwerp** in de zoekquery als u de exacte tekst of woordgroep kent die in de onderwerpregel van het bericht wordt gebruikt.

- Als u de exacte datum (of de periode) van het bericht weet, moet u de eigenschap **Ontvangen** in de zoekquery opnemen.

- Als u weet wie het bericht heeft verzonden, moet u de eigenschap **Van** in de zoekquery opnemen.

- Bekijk een voorbeeld van de zoekresultaten om te controleren of de zoekopdracht alleen het bericht (of de berichten) heeft geretourneerd die u wilt verwijderen.

- Gebruik de statistieken voor geschatte zoekresultaten (weergegeven in het detailvenster van de zoekopdracht in het Microsoft 365-compliancecentrum of met behulp van de cmdlet [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)) om het totale aantal resultaten te tellen.

Hier ziet u twee voorbeelden van query's om verdachte e-mailberichten te vinden.

- Deze query retourneert berichten die gebruikers hebben ontvangen tussen 13 april 2016 en 14 april 2016 en waarvan de onderwerpregel de woorden 'actie' en 'vereist' bevat.

  ```powershell
  (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
  ```

- Deze query retourneert berichten die zijn verzonden door chatsuwloginsset12345@outlook.com en die de exacte woordgroep 'Uw accountgegevens bijwerken' in het onderwerp bevatten.

  ```powershell
  (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
  ```

Hier volgt een voorbeeld van het gebruik van een query om een zoekopdracht te maken en te starten door de cmdlets **New-ComplianceSearch** en **Start-ComplianceSearch** uit te voeren om in alle postvakken in de organisatie te zoeken:

```powershell
$Search=New-ComplianceSearch -Name "Remove Phishing Message" -ExchangeLocation All -ContentMatchQuery '(Received:4/13/2016..4/14/2016) AND (Subject:"Action required")'
Start-ComplianceSearch -Identity $Search.Identity
```

## <a name="step-3-delete-the-message"></a>Stap 3: het bericht verwijderen

Nadat u een Inhoudszoekopdracht hebt gemaakt en verfijnd om het bericht te retourneren dat u wilt verwijderen en verbonden bent met de PowerShell van het Beveiligings- en compliancecentrum, bestaat de laatste stap eruit om de cmdlet **New-ComplianceSearchAction** uit te voeren om het bericht te verwijderen. U kunt het bericht snel of definitief verwijderen. Een snel verwijderd bericht wordt verplaatst naar de map Herstelbare items van een gebruiker en wordt bewaard totdat de bewaarperiode voor verwijderde items is verstreken. Definitief verwijderde berichten worden gemarkeerd voor permanente verwijdering uit het postvak en worden definitief verwijderd wanneer het postvak de volgende keer wordt verwerkt door de Assistent voor beheerde mappen. Als herstel van één item voor het postvak is ingeschakeld, worden deze verwijderde items definitief verwijderd nadat de bewaarperiode voor verwijderde items is verstreken. Als een postvak in de wacht is geplaatst, blijven verwijderde berichten behouden totdat de duur van het item verloopt of totdat de blokkade op het postvak wordt opgeheven.

In het volgende voorbeeld worden met de opdracht de zoekresultaten verwijderd die het resultaat zijn van een Inhoudszoekopdracht 'Phishingbericht verwijderen'.

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

Als u de items die door de inhoudszoekopdracht 'Phishingbericht verwijderen' worden geretourneerd definitief wilt verwijderen, moet u deze opdracht uitvoeren:

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

Wanneer u de vorige opdracht gebruikt om berichten (al dan niet definitief) te verwijderen, is de zoekopdracht die is opgegeven met de parameter *SearchName* de inhoudszoekopdracht die u in stap 1 hebt gemaakt.

Zie [New-ComplianceSearchAction](/powershell/module/exchange/New-ComplianceSearchAction) voor meer informatie.

## <a name="more-information"></a>Meer informatie

- **Hoe kom ik aan de status van het zoeken en verwijderen?**

  Voer **Get-ComplianceSearchAction** uit om de status van de verwijderbewerking te krijgen. Het object dat wordt gemaakt wanneer u de cmdlet **New-ComplianceSearchAction** wordt uitgevoerd, heeft de volgende indeling:  `<name of Content Search>_Purge`.

- **Wat gebeurt er nadat ik een bericht heb verwijderd?**

  Een bericht dat met de opdracht `New-ComplianceSearchAction -Purge -PurgeType HardDelete` wordt verwijderd, wordt verplaatst naar de map Verwijderd en kan niet worden gebruikt door de gebruiker. Nadat het bericht naar de map Verwijderd is verplaatst, blijft het bericht behouden gedurende de bewaarperiode voor verwijderde items, mits herstel van één item is ingeschakeld voor het postvak. (In Microsoft 365 is herstel van één item standaard ingeschakeld wanneer een nieuw postvak wordt gemaakt.) Nadat de bewaarperiode voor verwijderde items is verstreken, wordt het bericht gemarkeerd voor permanente verwijdering en wordt het verwijderd uit Microsoft 365 wanneer het postvak de volgende keer wordt verwerkt door de Assistent voor beheerde mappen.

  Als u de opdracht `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` gebruikt, worden berichten verplaatst naar de map Verwijderingen in de map Herstelbare items van de gebruiker. Ze worden niet direct uit Microsoft 365 verwijderd. De gebruiker kan berichten in de map Verwijderde items herstellen gedurende de duur op basis van de bewaarperiode voor verwijderde items die voor het postvak is geconfigureerd. Nadat deze bewaarperiode is verstreken (of als de gebruiker het bericht heeft opgeslagen voordat het verloopt), wordt het bericht verplaatst naar de map Opschoningen en kan het niet meer worden gebruikt door de gebruiker. Als het bericht eenmaal in de map Opschoningen staat, blijft het behouden gedurende de bewaarperiode voor verwijderde items die voor het postvak is geconfigureerd, mits herstel van één item is ingeschakeld voor het postvak. (In Microsoft 365 is herstel van één item standaard ingeschakeld wanneer een nieuw postvak wordt gemaakt.) Nadat de bewaarperiode voor verwijderde items is verstreken, wordt het bericht gemarkeerd voor permanente verwijdering en wordt het verwijderd uit Microsoft 365 wanneer het postvak de volgende keer wordt verwerkt door de Assistent voor beheerde mappen.

- **Wat moet ik doen als ik een bericht moet verwijderen uit meer dan 50.000 postvakken?**

  Zoals eerder vermeld, kunt u een zoekopdracht uitvoeren en deze op maximaal 50.000 postvakken uitvoeren (zelfs als minder dan 50.000 postvakken items bevatten die overeenkomen met de zoekopdracht). Als u een opdracht voor zoeken en opschonen moet uitvoeren en deze op meer dan 50.000 postvakken wilt uitvoeren, kunt u tijdelijke zoekmachtigingenfilters maken die het aantal postvakken waarin moet worden gezocht beperken tot minder dan 50.000. Als uw organisatie bijvoorbeeld postvakken bevat in verschillende afdelingen, staten of landen, kunt u een filter voor zoekmachtigingen voor postvakken maken op basis van een van deze postvakeigenschappen om te zoeken in een subset van postvakken in uw organisatie. Nadat u het filter voor zoekmachtigingen hebt gemaakt, maakt u de zoekopdracht (beschreven in stap 1) en verwijdert u het bericht (beschreven in stap 3). Vervolgens kunt u het filter bewerken om berichten in een andere set postvakken te zoeken en op te schonen. Zie [Het filteren van machtigingen configureren voor Inhoud zoeken](permissions-filtering-for-content-search.md) voor meer informatie over het maken van filters voor zoekmachtigingen.

- **Worden niet-geïndexeerde items in de zoekresultaten verwijderd?**

  Nee, met de opdracht New-ComplianceSearchAction -Purge worden niet-geïndexeerde items niet verwijderd.

- **Wat gebeurt er als een bericht wordt verwijderd uit een postvak waarvoor In-place bewaring of Bewaren van postvakgegevens vanwege juridische procedure is ingesteld of dat is toegewezen aan een bewaarbeleid van Microsoft 365?**

  Nadat het bericht is verwijderd en naar de map Verwijderd is verplaatst, blijft het bericht behouden totdat de duur van de wachttijd is verstreken. Als de duur van de wachttijd onbeperkt is, blijven items behouden totdat de blokkade wordt opgeheven of de duur van de wachttijd wordt gewijzigd.

- **Waarom is de werkstroom voor zoeken en verwijderen verdeeld over verschillende rollengroepen van het beveiligings- en compliancecentrum?**

  Zoals eerder uitgelegd, moet een persoon lid zijn van de rollengroep eDiscovery-manager of de rol Compliancezoekbeheer toegewezen krijgen om te kunnen zoeken in postvakken. Om berichten te verwijderen, moet een persoon lid zijn van de rollengroep Organisatiebeheer of aan de rol Zoeken en opschonen zijn toegewezen. Zo kunt u bepalen wie in postvakken in de organisatie kan zoeken en wie berichten kan verwijderen.
