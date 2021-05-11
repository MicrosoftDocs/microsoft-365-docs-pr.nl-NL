---
title: Basiscontrole instellen in Microsoft 365
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
description: In dit artikel wordt beschreven hoe u Basiscontrole kunt instellen, zodat u kunt zoeken naar auditactiviteiten die worden uitgevoerd door gebruikers en beheerders in uw organisatie.
ms.openlocfilehash: ff1f973226378e5408dfae1d467394a5a5153196
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314297"
---
# <a name="set-up-basic-auditing-in-microsoft-365"></a>Basiscontrole instellen in Microsoft 365

Met basiscontrole in Microsoft 365 kunt u zoeken naar auditrecords voor activiteiten die in de verschillende Microsoft 365 door gebruikers en beheerders worden uitgevoerd. Omdat Basisaudit standaard is ingeschakeld voor de meeste Microsoft 365- en Office 365-organisaties, hoeft u slechts een paar dingen te doen voordat u en anderen in uw organisatie het auditlogboek kunnen doorzoeken.

In dit artikel worden de volgende stappen beschreven die nodig zijn om Basiscontrole in te stellen.

![Stappen voor het instellen van Basiscontrole](../media/BasicAuditingWorkflow.png)

Deze stappen omvatten het waarborgen van de juiste organisatieabonnementen en gebruikerslicenties die nodig zijn voor het genereren en behouden van auditrecords en het toewijzen van machtigingen aan teamleden van uw beveiligingsbewerkingen, IT-, compliance- en juridische teams, zodat ze het auditlogboek kunnen doorzoeken.

Zie Basiscontrole [in Microsoft 365.](auditing-solutions-overview.md#basic-auditing)

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a>Stap 1: Organisatieabonnement en gebruikerslicenties controleren

Voor licenties voor basisaudits is het juiste organisatieabonnement vereist dat toegang biedt tot het zoekprogramma voor auditlogboek en licenties per gebruiker die nodig zijn voor het aanmelden en behouden van auditrecords.

Wanneer een gecontroleerde activiteit wordt uitgevoerd door een gebruiker of beheerder, wordt een auditrecord gegenereerd en opgeslagen in het auditlogboek voor uw organisatie. In Basiscontrole worden auditrecords 90 dagen bewaard en doorzocht in het auditlogboek.

Zie [Auditing solutions in](auditing-solutions-overview.md#licensing-requirements)Microsoft 365 voor een lijst met abonnements- en licentievereisten voor basisaudits.

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a>Stap 2: Machtigingen toewijzen om het auditlogboek te doorzoeken

Beheerders en leden van onderzoeksteams moeten de rol auditlogboeken of auditlogboeken View-Only auditlogboeken in Exchange Online om het auditlogboek te doorzoeken. Deze rollen worden standaard toegewezen aan de rollengroepen Compliancebeheer en Organisatiebeheer op de pagina **Machtigingen** in het Exchange-beheercentrum. Globale beheerders in Office 365 en Microsoft 365 worden automatisch toegevoegd als leden van de rollengroep Organisatiebeheer in Exchange Online. Als u de gebruiker het auditlogboek wilt laten doorzoeken met minimale rechten, kunt u in Exchange Online een aangepaste rollengroep maken, de rol Auditlogboeken alleen-weergeven of Auditlogboeken toevoegen en vervolgens de gebruiker toevoegen als lid van de nieuwe rollengroep. Zie voor meer informatie [Rollengroepen beheren in Exchange Online](/Exchange/permissions-exo/role-groups).

In de volgende schermafbeelding ziet u de twee auditgerelateerde rollen die zijn toegewezen aan de rollengroep Organisatiebeheer in het Exchange beheercentrum.

![Auditrollen die zijn toegewezen aan rollengroep in Exchange Online](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a>Stap 3: Het auditlogboek doorzoeken

Nu kunt u het auditlogboek doorzoeken in het Microsoft 365 compliancecentrum.

1. Ga naar <https://compliance.microsoft.com> en meld u aan met een account dat de juiste controlemachtigingen heeft gekregen.

2. Klik in het linkernavigatiedeelvenster van het Microsoft 365 compliancecentrum op **Alles weergeven** en klik vervolgens op **Controleren.**

3. Configureer **de zoekopdracht** op de pagina Controle met behulp van de volgende voorwaarden op het **tabblad** Zoeken. 

   ![Configuratie-instellingen voor zoeken in auditlogboek](../media/AuditLogSearchToolMCCCallouts.png)

   1. **Datum en tijdbereik.** Selecteer een bereik voor de datum en tijd om de gebeurtenissen weer te geven die in die periode hebben plaatsgevonden.  De datum en tijd worden op lokale tijd weergegeven. De laatste zeven dagen zijn standaard geselecteerd.
  
   2. **Activiteiten**. Selecteer de activiteiten die u wilt zoeken. Gebruik het zoekvak om te zoeken naar activiteiten die u aan de lijst wilt toevoegen. Zie Gecontroleerde activiteiten voor een gedeeltelijke lijst met gecontroleerde [activiteiten.](search-the-audit-log-in-security-and-compliance.md#audited-activities) Laat dit vak leeg als u items wilt retourneren voor alle gecontroleerde activiteiten.
  
   3. **Gebruikers**.  Klik in dit vak en typ de naam van gebruikers om zoekresultaten weer te geven. De controlelogboekgegevens voor de geselecteerde activiteiten die worden uitgevoerd door de gebruikers die u in dit vak selecteert, worden weergegeven in de lijst met resultaten. Laat dit vak leeg als u vermeldingen wilt zien voor alle gebruikers (en serviceaccounts) in uw organisatie.
  
   4. **Bestand, map of site**. Typ een of meer bestanden of mappen om te zoeken naar activiteiten die betrekking hebben op het mapbestand dat het opgegeven trefwoord bevat. U kunt ook een URL van een bestand of map opgeven. Als u een URL van een bestand of map gebruikt, moet u het volledige URL-pad typen of als u een deel van de URL typt, geen speciale tekens of spaties bevatten. Laat dit vak leeg als u vermeldingen wilt zien voor alle bestanden en mappen in uw organisatie.

4. Klik **op Zoeken** om de zoekopdracht uit te voeren.

Er wordt een nieuwe pagina weergegeven met de zoekactie in het auditlogboek. Wanneer de zoekopdracht is voltooid, worden auditrecords weergegeven op de pagina. Klik op een record om een flyoutpagina met gedetailleerde eigenschappen weer te geven.

Zie Het auditlogboek in het [compliancecentrum doorzoeken](search-the-audit-log-in-security-and-compliance.md)voor meer gedetailleerde instructies.
