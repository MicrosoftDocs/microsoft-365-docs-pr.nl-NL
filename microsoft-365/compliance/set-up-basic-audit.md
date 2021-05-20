---
title: Basisaudit instellen in Microsoft 365
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
description: In dit artikel wordt beschreven hoe u Basisaudit instelt, zodat u kunt beginnen met het zoeken naar controleactiviteiten die worden uitgevoerd door gebruikers en beheerders in uw organisatie.
ms.openlocfilehash: 59b5c85003ef0e19f7d3dd7417f764f446244652
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52564823"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a>Basisaudit instellen in Microsoft 365

Met Basic Audit in Microsoft 365 kunt u zoeken naar controlerecords voor activiteiten die in de verschillende Microsoft 365 services door gebruikers en beheerders worden uitgevoerd. Omdat Basic Audit standaard is ingeschakeld voor de meeste Microsoft 365- en Office 365 organisaties, hoeft u slechts een paar dingen te doen voordat u en anderen in uw organisatie in het controlelogboek kunnen zoeken.

In dit artikel worden de volgende stappen besproken die nodig zijn om basisaudit in te stellen.

![Stappen voor het instellen van basisaudit](../media/BasicAuditingWorkflow.png)

Deze stappen omvatten het waarborgen van de juiste organisatie-abonnementen en gebruikerslicenties die nodig zijn om auditrecords te genereren en te bewaren en het toewijzen van machtigingen aan teamleden van uw beveiligingsactiviteiten, IT, naleving en juridische teams, zodat het auditlogboek kan worden doorzocht.

Zie [Basisaudit in Microsoft 365](auditing-solutions-overview.md#basic-audit)voor meer informatie.

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a>Stap 1: Organisatieabonnement en gebruikerslicenties verifiëren

Licenties voor basiscontrole vereisen het juiste organisatieabonnement dat toegang biedt tot het zoekprogramma voor controlelogboeken en licenties per gebruiker die nodig zijn om controlerecords te registreren en te bewaren.

Wanneer een gecontroleerde activiteit wordt uitgevoerd door een gebruiker of beheerder, wordt een auditrecord gegenereerd en opgeslagen in het auditlogboek voor uw organisatie. In Basic Audit worden controlerecords gedurende 90 dagen bewaard en doorzoekbaar in het auditlogboek.

Zie Controleoplossingen in Microsoft 365 voor een lijst [met abonnements-](auditing-solutions-overview.md#licensing-requirements)en licentievereisten voor Basisaudit.

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a>Stap 2: Machtigingen toewijzen om in het controlelogboek te zoeken

Beheerders en leden van onderzoeksteams moeten de rol View-Only auditlogboeken of controlelogboeken in Exchange Online krijgen om in het controlelogboek te zoeken. Deze rollen worden standaard toegewezen aan de rollengroepen Compliancebeheer en Organisatiebeheer op de pagina **Machtigingen** in het Exchange-beheercentrum. Globale beheerders in Office 365 en Microsoft 365 worden automatisch toegevoegd als leden van de rolgroep Organisatiebeheer in Exchange Online. Als u de gebruiker het auditlogboek wilt laten doorzoeken met minimale rechten, kunt u in Exchange Online een aangepaste rollengroep maken, de rol Auditlogboeken alleen-weergeven of Auditlogboeken toevoegen en vervolgens de gebruiker toevoegen als lid van de nieuwe rollengroep. Zie voor meer informatie [Rollengroepen beheren in Exchange Online](/Exchange/permissions-exo/role-groups).

In de volgende schermafbeelding ziet u de twee controlegerelateerde rollen die zijn toegewezen aan de rolgroep Organisatiebeheer in het Exchange-beheercentrum.

![Controlerollen toegewezen aan rolgroep in Exchange Online](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a>Stap 3: Doorzoek het auditlogboek

Nu bent u klaar om het controlelogboek te doorzoeken in het Microsoft 365 compliance center.

1. Ga naar <https://compliance.microsoft.com> en meld u aan met een account waaraan de juiste controlemachtigingen zijn toegewezen.

2. Klik in het linkernavigatiedeelvenster van het Microsoft 365 compliancecentrum op **Alles weergeven** en klik vervolgens op **Controleren**.

3. Configureer de zoekopdracht op de pagina **Controle** met de volgende voorwaarden op het tabblad **Zoeken.** 

   ![Configuratie-instellingen voor het zoeken naar controlelogboeken](../media/AuditLogSearchToolMCCCallouts.png)

   1. **Datum en tijdsbereik**. Selecteer een bereik voor de datum en tijd om de gebeurtenissen weer te geven die in die periode hebben plaatsgevonden.  De datum en tijd worden op lokale tijd weergegeven. De laatste zeven dagen zijn standaard geselecteerd.
  
   2. **Activiteiten**. Selecteer de activiteiten waarnaar u wilt zoeken. Gebruik het zoekvak om te zoeken naar activiteiten die aan de lijst moeten worden toegevoegd. Zie Gecontroleerde activiteiten voor een gedeeltelijke lijst van gecontroleerde [activiteiten](search-the-audit-log-in-security-and-compliance.md#audited-activities). Laat dit vak leeg om posten voor alle gecontroleerde activiteiten te retourneren.
  
   3. **Gebruikers**.  Klik in dit vak en begin met het typen van de naam van gebruikers waarvoor u zoekresultaten wilt weergeven. De controlelogboekvermeldingen voor de geselecteerde activiteiten die worden uitgevoerd door de gebruikers die u in dit vak selecteert, worden weergegeven in de lijst met resultaten. Laat dit vak leeg als u vermeldingen wilt zien voor alle gebruikers (en serviceaccounts) in uw organisatie.
  
   4. **Bestand, map of site**. Typ een of alle bestands- of mapnamen om te zoeken naar activiteit met betrekking tot het mapbestand dat het opgegeven trefwoord bevat. U kunt ook een URL van een bestand of map opgeven. Als u een URL van een bestand of map gebruikt, moet u ervoor zorgen dat u het volledige URL-pad typt of dat als u een gedeelte van de URL typt, geen speciale tekens of spaties worden opgenomen. Laat dit vak leeg als u vermeldingen wilt zien voor alle bestanden en mappen in uw organisatie.

4. Klik **op Zoeken** om de zoekopdracht uit te voeren.

Er wordt een nieuwe pagina weergegeven waarop wordt weergegeven dat de zoekopdracht in het controlelogboek wordt uitgevoerd. Wanneer de zoekopdracht is voltooid, worden controlerecords op de pagina weergegeven. Klik op een record om een flyout-pagina met gedetailleerde eigenschappen weer te geven.

Zie [Het controlelogboek doorzoeken in het nalevingscentrum voor](search-the-audit-log-in-security-and-compliance.md)meer gedetailleerde instructies.
