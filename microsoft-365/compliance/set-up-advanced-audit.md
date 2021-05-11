---
title: Geavanceerde audit instellen in Microsoft 365
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
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In dit artikel wordt beschreven hoe u Advanced Audit in kunt stellen, zodat u gerechtelijke onderzoeken kunt uitvoeren wanneer gebruikersaccounts worden gehackt of om andere beveiligingsgerelateerde incidenten te onderzoeken.
ms.openlocfilehash: d1752ee7714056254a6c0e5c009aa9aa79ddff3b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314301"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a>Geavanceerde audit instellen in Microsoft 365

Als uw organisatie een abonnements- en eindgebruikerslicentie heeft die Geavanceerde controle ondersteunt, voert u de volgende stappen uit om de extra mogelijkheden in Advanced Audit in te stellen en te gebruiken.

![Werkstroom voor het instellen van geavanceerde controle](../media/AdvancedAuditWorkflow.png)

## <a name="step1-set-up-advanced-audit-for-users"></a>Stap1: Geavanceerde controle instellen voor gebruikers

Geavanceerde auditfuncties, zoals de mogelijkheid om belangrijke gebeurtenissen, zoals MailItemsAccessed en Verzenden, bij te houden, vereisen een geschikte E5-licentie die aan gebruikers is toegewezen. Daarnaast moet het advanced auditing app/service plan zijn ingeschakeld voor deze gebruikers. Als u wilt controleren of de app Geavanceerd controleren is toegewezen aan gebruikers, voert u de volgende stappen voor elke gebruiker uit:

1. Ga in [Microsoft 365 beheercentrum](https://admin.microsoft.com/Adminportal)naar **Gebruikers**  >  **actieve gebruikers** en selecteer een gebruiker.

2. Klik op de flyoutpagina met gebruikerseigenschappen op **Licenties en apps.**

3. Controleer in **de sectie** Licenties of aan de gebruiker een E5-licentie is toegewezen of dat aan de gebruiker een geschikte invoeglicentie is toegewezen. Zie Licentievereisten voor geavanceerde audit voor een lijst met licenties die Geavanceerde controle [ondersteunen.](auditing-solutions-overview.md#advanced-audit-1)

4. Vouw de **sectie Apps** uit en controleer of Microsoft 365 **selectievakje** Geavanceerd controleren is ingeschakeld.

5. Als het selectievakje niet is geselecteerd, selecteert u het selectievakje en klikt u op **Wijzigingen opslaan.**

   De logboekregistratie van auditrecords voor MailItemsAccessed en Verzenden begint binnen 24 uur. U moet stap 3 uitvoeren om te beginnen met het registreren van twee andere belangrijke gebeurtenissen voor geavanceerde audit: SearchQueryInitiatedExchange en SearchQueryInitiatedSharePoint.

Voor organisaties die licenties toewijzen aan groepen gebruikers met behulp van groepslicenties, moet u de licentietoewijzing voor Microsoft 365 Advanced Auditing voor de groep uitschakelen. Nadat u de wijzigingen hebt op slaan, controleert u of Microsoft 365 Geavanceerd controleren is uitgeschakeld voor de groep. Schakel vervolgens de licentietoewijzing voor de groep weer in. Zie Licenties toewijzen aan gebruikers op basis van [groepslidmaatschap in](/azure/active-directory/users-groups-roles/licensing-groups-assign)Azure Active Directory voor instructies over groepslicenties.

Als u de postvakacties hebt aangepast die zijn aangemeld bij gebruikerspostvakken of gedeelde postvakken, worden nieuwe belangrijke gebeurtenissen die door Microsoft zijn uitgebracht, niet automatisch gecontroleerd op die postvakken. Zie de sectie 'Standaard aangemelde postvakacties wijzigen of herstellen' in Postvakcontrole beheren voor informatie over het wijzigen van de postvakacties die worden gecontroleerd voor elk [aanmeldingstype.](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)

## <a name="step-2-enable-crucial-events"></a>Stap 2: Cruciale gebeurtenissen inschakelen

U moet twee belangrijke gebeurtenissen (SearchQueryInitiatedExchange en SearchQueryInitiatedSharePoint) inschakelen om te worden geregistreerd wanneer gebruikers zoekopdrachten uitvoeren in Exchange Online en SharePoint Online. Als u wilt dat deze twee gebeurtenissen worden gecontroleerd voor gebruikers, moet u de volgende opdracht (voor elke gebruiker) uitvoeren in [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

In een multi-geoomgeving moet u  de vorige opdracht Postvak instellen uitvoeren in het bos waar het postvak van de gebruiker zich bevindt. Voer de volgende opdracht uit om de postvaklocatie van de gebruiker te identificeren: 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

Als de opdracht voor het inschakelen van het controleren van zoekquery's eerder is uitgevoerd in een forest dat anders is dan het postvak van de gebruiker, moet u de waarde SearchQueryInitiated verwijderen uit het postvak van de gebruiker door deze uit te voeren en vervolgens toe te voegen aan het postvak van de gebruiker in het forest waar het postvak van de gebruiker `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` zich bevindt.

## <a name="step-3-set-up-audit-retention-policies"></a>Stap 3: Beleid voor controlebewaring instellen

Naast het standaardbeleid dat Exchange-, SharePoint- en Azure AD-auditrecords één jaar behoudt, kunt u aanvullende bewaarbeleidsregels voor auditlogboek maken om te voldoen aan de vereisten van de beveiligingsbewerkingen, IT- en complianceteams van uw organisatie. Zie voor meer informatie [Bewaarbeleid voor auditlogboeken beheren](audit-log-retention-policies.md).

## <a name="step-4-search-for-crucial-events"></a>Stap 4: Zoeken naar belangrijke gebeurtenissen

Nu u geavanceerde controle hebt ingesteld voor uw organisatie, kunt u zoeken naar belangrijke gebeurtenissen en andere activiteiten bij het uitvoeren van gerechtelijke onderzoeken. Nadat u stap 1 en stap 2 hebt uitgevoerd, kunt u in het auditlogboek zoeken naar belangrijke gebeurtenissen en andere activiteiten tijdens het gerechtelijk onderzoek naar gecompromitteerde accounts en andere soorten beveiligings- of complianceonderzoeken. Zie Geavanceerde controle gebruiken om gecompromitteerde accounts te onderzoeken voor meer informatie over het uitvoeren van een onderzoek naar gecompromitteerde [gebruikersaccounts](mailitemsaccessed-forensics-investigations.md)met behulp van de cruciale gebeurtenis MailItemsAccessed.
