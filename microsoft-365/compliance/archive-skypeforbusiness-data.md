---
title: Een connector instellen voor het archiveren van Skype voor Bedrijven gegevens in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Informatie over het instellen en gebruiken van een verbindingslijn in de Microsoft 365-compliancecentrum gegevens importeren en archiveren van Skype voor Bedrijven naar Microsoft 365.
ms.openlocfilehash: 93128af0c7f305cb2bef55efd5520de77555a222
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054819"
---
# <a name="set-up-a-connector-to-archive-skype-for-business-data-preview"></a>Een verbindingslijn instellen om gegevens Skype voor Bedrijven archiveren (voorbeeld)

Gebruik een Veritas-connector in de Microsoft 365-compliancecentrum om gegevens van het Skype voor Bedrijven-platform te importeren en te archiveren in gebruikerspostvakken in uw Microsoft 365 organisatie. Veritas biedt een [Skype voor Bedrijven](https://www.veritas.com/en/au/insights/merge1/skype-for-business) connector die is geconfigureerd om items uit de gegevensbron van derden vast te leggen (op regelmatige basis) en deze items te importeren in Microsoft 365. De connector converteert de inhoud, zoals berichten tussen gebruikers, permanente chats en vergaderingsberichten van Skype voor Bedrijven naar een e-mailberichtindeling en importeert deze items vervolgens in het postvak van de gebruiker in Microsoft 365.

Nadat Skype voor Bedrijven gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels. Met een Skype voor Bedrijven verbindingslijn voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-skype-for-business-data"></a>Overzicht van het archiveren Skype voor Bedrijven gegevens

In het volgende overzicht wordt uitgelegd hoe u een verbindingslijn gebruikt om de Skype voor Bedrijven gegevens in Microsoft 365.

![Archiveringswerkstroom voor Skype voor Bedrijven gegevens](../media/SkypeforBusinessConnectorWorkflow.png)

1. Uw organisatie werkt samen met Skype voor Bedrijven voor het instellen en configureren van een Skype voor Bedrijven site.

2. Elke 24 uur Skype voor Bedrijven items gekopieerd naar de Veritas Merge1-site. De connector converteert ook Skype voor Bedrijven items naar een e-mailberichtindeling.

3. De Skype voor Bedrijven connector die u maakt in de Microsoft 365-compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en draagt de Skype voor Bedrijven-inhoud over naar een veilige Azure Storage-locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde items in de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup) Er wordt een submap in  de map Postvak SKYPE VOOR BEDRIJVEN gemaakt in de postvakken van de gebruiker en items worden geïmporteerd in die map. De verbindingslijn doet dit met behulp van de waarde van de eigenschap *E-mail.* Elk Skype voor Bedrijven item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer aan het item.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

- Maak een Merge1-account voor Microsoft-connectors. Neem hiervoor contact op met [Veritas Customer Support.](https://www.veritas.com/form/requestacall/ms-connectors-contact.html) U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de Skype voor Bedrijven maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-skype-for-business-connector"></a>Stap 1: De verbindingslijn Skype voor Bedrijven instellen

De eerste stap is toegang tot de pagina Gegevensconnectoren in de Microsoft 365-compliancecentrum en een **verbindingslijn** maken voor Skype voor Bedrijven gegevens.

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectors**  >  **Skype voor Bedrijven.**

2. Klik op **Skype voor Bedrijven** pagina productbeschrijving op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-skype-for-business-on-the-veritas-merge1-site"></a>Stap 2: De Skype voor Bedrijven op de Veritas Merge1-site configureren

De tweede stap is het configureren van Skype voor Bedrijven verbindingslijn op de Veritas Merge1-site. Zie Gebruikershandleiding voor connectors van derden samenvoegen voor informatie over het configureren Skype voor Bedrijven [verbindingslijn.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Skype%20for%20Business%20%20User%20Guide.pdf)

Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard Verbindingslijn in de Microsoft 365-compliancecentrum weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de verbindingslijn in de Microsoft 365-compliancecentrum, volgt u de volgende stappen:

1. Schakel op **de pagina Skype voor Bedrijven gebruikers automatisch toewijzen Microsoft 365** gebruikers in. De Skype voor Bedrijven items bevatten een eigenschap met de naam E-mail, die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** controleer uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-skype-for-business-connector"></a>Stap 4: De verbindingslijn Skype voor Bedrijven controleren

Nadat u de verbindingslijn Skype voor Bedrijven, kunt u de verbindingslijnstatus in de Microsoft 365-compliancecentrum.

1. Ga naar <https://compliance.microsoft.com/> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens Skype voor Bedrijven verbindingslijn om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat. 

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.
