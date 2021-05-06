---
title: Kennisgevingssjablonen voor insiderrisicobeheer
description: Meer informatie over kennisgevingssjablonen voor insiderrisicobeheer in Microsoft 365
keywords: Microsoft 365, insider risk management, risk management, compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2020
ms.locfileid: "52161517"
---
# <a name="insider-risk-management-notice-templates"></a>Kennisgevingssjablonen voor insiderrisicobeheer

Met kennisgevingssjablonen voor insiderrisicobeheer kunt u e-mailberichten verzenden naar gebruikers wanneer hun activiteiten een beleidsmatch en waarschuwing genereren. In de meeste gevallen zijn gebruikersacties die waarschuwingen genereren het resultaat van fouten of onbedoelde activiteiten zonder slechte bedoelingen. Kennisgevingen dienen als eenvoudige herinneringen aan gebruikers om voorzichtiger te zijn, om koppelingen te geven naar informatie voor bijscholing of naar bronnen van het bedrijfsbeleid. Kennisgevingen kunnen een belangrijk onderdeel zijn van uw interne compliancetrainingsprogramma en kunnen helpen bij het maken van een gedocumenteerd controlespoor voor gebruikers met terugkerende risicoactiviteiten.

Maak kennisgevingssjablonen als u gebruikers een e-mailherinneringsbericht wilt sturen voor beleidswedstrijden als onderdeel van het probleemoplossingsproces. Kennisgevingen kunnen alleen worden verzonden naar het e-mailadres van de gebruiker dat is gekoppeld aan de specifieke waarschuwing die wordt gecontroleerd. Wanneer u een kennisgevingssjabloon selecteert die moet worden toegepast op een beleidsmatch, kunt u ervoor kiezen om de veldwaarden te accepteren die in de sjabloon zijn gedefinieerd of om de velden zo nodig te overschrijven.

## <a name="notice-templates-dashboard"></a>Dashboard Met kennisgevingssjablonen

In het dashboard Berichtensjablonen wordt een lijst met geconfigureerde kennisgevingssjablonen weergegeven en kunt u nieuwe **kennisgevingssjablonen** maken. De kennisgevingssjablonen worden weergegeven in omgekeerde datum volgorde met de meest recente kennisgevingssjabloon die eerst wordt weergegeven.

![Dashboard met kennisgevingssjabloon voor insiderrisicobeheer](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>HTML voor kennisgevingen

Als u meer wilt maken dan een eenvoudig e-mailbericht op basis van tekst voor meldingen, kunt u een gedetailleerder bericht maken met HTML in het berichttekstveld van een kennisgevingssjabloon. In het volgende voorbeeld wordt de hoofdindeling van het bericht weergegeven voor een basissjabloon voor e-mailmeldingen op basis van HTML:

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> Html href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.

## <a name="create-a-new-notice-template"></a>Een nieuwe kennisgevingssjabloon maken

Als u een nieuwe kennisgevingssjabloon voor insiderrisicobeheer wilt maken, gebruikt u de kennisgevingswizard in **de oplossing** voor insiderrisicobeheer in het Microsoft 365 compliancecentrum.

Volg de volgende stappen om een nieuwe kennisgevingssjabloon voor insiderrisicobeheer te maken:

1. Ga in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer het **tabblad Kennisgevingssjablonen.**
2. Selecteer **Kennisgevingssjabloon maken** om de wizard Kennisgeving te openen.
3. Vul op **de pagina Een nieuwe kennisgevingssjabloon** maken de volgende velden in:
    - **Naam van sjabloon:** Voer een vriendelijke naam in voor de melding. Deze naam wordt weergegeven in de lijst met aankondigingen op het aankondigingsdashboard en in de lijst met aankondigingenselectie bij het verzenden van kennisgevingen vanuit een zaak.
    - **Verzenden vanuit**: Voer het e-mailadres van de afzender in voor de melding. Dit adres wordt weergegeven in het **veld Van:** in alle kennisgevingen die naar gebruikers worden verzonden, tenzij dit is gewijzigd bij het verzenden van een melding vanuit een zaak.
    - **CC- en BCC-velden:** Optionele gebruikers of groepen die op de hoogte worden gesteld van de beleidsmatch, geselecteerd in de Active Directory voor uw abonnement.
    - **Onderwerp:** Informatie die wordt weergegeven in de onderwerpregel van het bericht, ondersteunt teksttekens.
    - **Berichttekst:** informatie die wordt weergegeven in de berichttekst, ondersteunt tekst- of HTML-waarden.
4. Selecteer **Maken om** de kennisgevingssjabloon te maken en op te slaan of selecteer **Annuleren** om te sluiten zonder de kennisgevingssjabloon op te slaan.

## <a name="update-a-notice-template"></a>Een kennisgevingssjabloon bijwerken

Als u een bestaande kennisgevingssjabloon voor insiderrisicobeheer wilt bijwerken, gaat u als volgt te werk:

1. Ga in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer het **tabblad Kennisgevingssjablonen.**
2. Selecteer in het kennisgevingsdashboard de kennisgevingssjabloon die u wilt beheren.
3. Selecteer bewerken op de pagina **Aankondigingsdetails**
4. Op de **pagina** Bewerken kunt u de volgende velden bewerken:
    - **Naam van sjabloon:** Voer een nieuwe vriendschappelijke naam in voor de melding. Deze naam wordt weergegeven in de lijst met aankondigingen op het aankondigingsdashboard en in de lijst met aankondigingenselectie bij het verzenden van kennisgevingen vanuit een zaak.
    - **Verzenden vanuit**: Het e-mailadres van de afzender bijwerken voor de melding. Dit adres wordt weergegeven in het **veld Van:** in alle kennisgevingen die naar gebruikers worden verzonden, tenzij dit is gewijzigd bij het verzenden van een melding vanuit een zaak.
    - **CC- en BCC-velden:** Werk optionele gebruikers of groepen bij om op de hoogte te worden gesteld van de beleidsmatch, geselecteerd in de Active Directory voor uw abonnement.
    - **Onderwerp:** Informatie bijwerken die wordt weergegeven in de onderwerpregel van het bericht, ondersteunt teksttekens.
    - **Berichttekst:** Informatie bijwerken die wordt weergegeven in de berichttekst, ondersteunt tekst- of HTML-waarden.
5. Selecteer **Opslaan om** de melding bij te werken en op te slaan of selecteer **Annuleren** om te sluiten zonder de kennisgevingssjabloon op te slaan.

## <a name="delete-a-notice-template"></a>Een kennisgevingssjabloon verwijderen

Als u een bestaande kennisgevingssjabloon voor insiderrisicobeheer wilt verwijderen, gaat u als volgt te werk:

1. Ga in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer het **tabblad Kennisgevingssjablonen.**
2. Selecteer in het aankondigingsdashboard de kennisgevingssjabloon die u wilt verwijderen.
3. Selecteer het **pictogram** Verwijderen op de werkbalk.
4. Als u de kennisgevingssjabloon wilt verwijderen, **selecteert u Ja** in het dialoogvenster Verwijderen. Als u het verwijderen wilt annuleren, selecteert u **Annuleren.**
