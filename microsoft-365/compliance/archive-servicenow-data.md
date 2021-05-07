---
title: Een connector instellen voor het archiveren van ServiceNow-gegevens in Microsoft 365
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
description: Beheerders kunnen een connector instellen voor het importeren en archiveren van ServiceNow-gegevens van Veritas naar Microsoft 365. Met deze connector kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365. Nadat u deze gegevens hebt gearchiveerd, kunt u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, gebruiken om gegevens van derden te beheren.
ms.openlocfilehash: 8f1f56f79d3cdd0e198f03d948837249d3e0ff3b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162316"
---
# <a name="set-up-a-connector-to-archive-servicenow-data"></a>Een verbindingslijn instellen voor het archiveren van ServiceNow-gegevens

Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens van het ServiceNow-platform te importeren en te archiveren naar postvakken van gebruikers in uw Microsoft 365 organisatie. Veritas biedt een [ServiceNow-connector](https://globanet.com/servicenow/) die items uit de gegevensbron van derden vast legt en deze items importeert in Microsoft 365. De connector converteert de inhoud, zoals liveberichten, bijlagen en berichten van ServiceNow naar een e-mailberichtindeling en importeert deze items vervolgens in postvakken van gebruikers in Microsoft 365.

Nadat ServiceNow-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels. Als u een ServiceNow-connector gebruikt voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-servicenow-data"></a>Overzicht van het archiveren van ServiceNow-gegevens

In het volgende overzicht wordt uitgelegd hoe u een verbindingslijn gebruikt om de ServiceNow-gegevens te archiveren in Microsoft 365.

![Archiveringswerkstroom voor ServiceNow-gegevens](../media/ServiceNowConnectorWorkflow.png)

1. Uw organisatie werkt samen met ServiceNow om een ServiceNow-site in te stellen en te configureren.

2. Eenmaal per 24 uur worden ServiceNow-items gekopieerd naar de Veritas Merge1-site. De connector converteert ook ServiceNow-items naar een e-mailberichtindeling.

3. De ServiceNow-connector die u in het Microsoft 365-compliancecentrum maakt, maakt elke dag verbinding met de Veritas Merge1-site en draagt de ServiceNow-inhoud over naar een veilige Azure Storage-locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde items in de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup) Er wordt een submap in de map Postvak IN met de naam **ServiceNow** gemaakt in de postvakken van de gebruiker en items worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk ServiceNow-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer aan het item.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://www.veritas.com/content/support/)om een account te maken. U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- Maak een ServiceNow-toepassing om gegevens op te halen uit uw ServiceNow-account. Zie Gebruikershandleiding voor connectors van derden samenvoegen voor stapsgewijse instructies over het maken [van de toepassing.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)

- De gebruiker die de ServiceNow-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-servicenow-connector"></a>Stap 1: De ServiceNow-connector instellen

De eerste stap is toegang tot de pagina Gegevensconnectoren in het Microsoft 365 compliancecentrum en een **verbindingslijn** maken voor ServiceNow-gegevens.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectoren**  >  **ServiceNow**.

2. Klik op **de pagina ServiceNow-productbeschrijving** op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-servicenow-on-the-veritas-merge1-site"></a>Stap 2: De ServiceNow configureren op de Veritas Merge1-site

De tweede stap is het configureren van de ServiceNow-connector op de Veritas Merge1-site. Zie Gebruikershandleiding voor [connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)van derden samenvoegen voor informatie over het configureren van de ServiceNow-connector.

Nadat u op Opslaan & Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard Verbindingslijn in Microsoft 365 compliancecentrum weergegeven. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de verbindingslijn wilt voltooien in het Microsoft 365 compliancecentrum, volgt u de volgende stappen:

1. Schakel automatische gebruikerstoewijzing in **op de pagina Microsoft 365 Gebruikers** toewijzen. De ServiceNow-items bevatten een eigenschap met de naam E-mail, die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** controleer uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-servicenow-connector"></a>Stap 4: De ServiceNow-connector controleren

Nadat u de ServiceNow-verbindingslijn hebt gebruikt, kunt u de status van de verbindingslijn weergeven in het Microsoft 365 compliancecentrum.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de **ServiceNow-verbindingslijn** om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.