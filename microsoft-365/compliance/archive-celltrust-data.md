---
title: Een connector instellen voor het archiveren van CellTrust-gegevens in Microsoft 365
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
description: Beheerders kunnen een connector instellen voor het importeren en archiveren van CellTrust-gegevens van Veritas naar Microsoft 365. Met deze connector kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365. Nadat u deze gegevens hebt gearchiveerd, kunt u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, gebruiken om gegevens van derden te beheren.
ms.openlocfilehash: 855d48303c7c35c32951105799aa117675820420
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162359"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a>Een verbindingslijn instellen voor het archiveren van CellTrust-gegevens

Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens van het CellTrust-platform te importeren en te archiveren naar postvakken van gebruikers in uw Microsoft 365 organisatie. Veritas biedt een [CellTrust-connector](https://globanet.com/celltrust/) die items uit de gegevensbron van derden vast legt en deze items importeert naar Microsoft 365. De connector converteert de inhoud van Sms berichten van CellTrust-accounts naar een e-mailberichtindeling en importeert deze items vervolgens in het postvak van de gebruiker in Microsoft 365.

Nadat CellTrust-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance. Als u een CellTrust-connector gebruikt voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-celltrust-data"></a>Overzicht van het archiveren van CellTrust-gegevens

In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn voor het archiveren van CellTrust-gegevens in Microsoft 365.

![Archiveringswerkstroom voor CellTrust-gegevens](../media/CellTrustConnectorWorkflow.png)

1. Uw organisatie werkt samen met CellTrust om een CellTrust-site in te stellen en te configureren.

2. Elke 24 uur worden CellTrust-items gekopieerd naar de Veritas Merge1-site. De verbindingslijn converteert ook de inhoud van een bericht naar een e-mailberichtindeling.

3. De CellTrust-connector die u in het Microsoft 365-compliancecentrum maakt, maakt elke dag verbinding met de Veritas Merge1-site en brengt de berichten over naar een veilige Azure Storage-locatie in de Microsoft-cloud.

4. De automatische gebruikerstoewijzing als verbindingslijn importeert items naar de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup) Er wordt een submap in de map Postvak IN met de naam **CellTrust** gemaakt in de postvakken van de gebruiker en de berichtitems worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk CellTrust-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://www.veritas.com/content/support/)om een account te maken. U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de CellTrust-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-celltrust-connector"></a>Stap 1: De CellTrust-connector instellen

De eerste stap is toegang tot de gegevensconnectoren in het Microsoft 365 compliancecentrum en een **verbindingslijn** maken voor CellTrust-gegevens.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectoren** \> **CellTrust.**

2. Klik op **de pagina Productbeschrijving van CellTrust** op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-celltrust-connector-on-the-veritas-merge1-site"></a>Stap 2: De CellTrust-connector configureren op de Veritas Merge1-site

De tweede stap is het configureren van de CellTrust-connector op de Veritas Merge1-site. Zie Gebruikershandleiding voor [connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf)van derden samenvoegen voor informatie over het configureren van de CellTrust-connector.

Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard verbindingslijn in het Microsoft 365 compliancecentrum weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de connector wilt voltooien die is ingesteld in het Microsoft 365 compliancecentrum, volgt u de volgende stappen:

1. Schakel op **de pagina CellTrust-gebruikers toewijzen Microsoft 365 gebruikers automatisch** toewijzen in. De CellTrust-items bevatten een eigenschap met de naam E-mail, die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** bekijk uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-celltrust-connector"></a>Stap 4: De CellTrust-verbindingslijn controleren

Nadat u de CellTrust-verbindingslijn hebt maken, kunt u de status van de verbindingslijn weergeven in het Microsoft 365 compliancecentrum.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de **CellTrust-verbindingslijn** om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.