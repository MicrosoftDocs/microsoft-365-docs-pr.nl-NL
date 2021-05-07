---
title: Een verbindingslijn instellen voor het archiveren van draaitabelgegevens in Microsoft 365
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
description: Beheerders kunnen een verbindingslijn instellen voor het importeren en archiveren van draaigegevens van Veritas in Microsoft 365. Met deze verbindingslijn kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365, zodat u compliancefuncties zoals juridische bewaring, inhoud zoeken en bewaarbeleid kunt gebruiken om de gegevens van derden van uw organisatie te beheren.
ms.openlocfilehash: 8e88f5166ebcc4d1285a81e041b6d97be46786e3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162345"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a>Een verbindingslijn instellen voor het archiveren van draaitabelgegevens

Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens van het draaitabelplatform te importeren en te archiveren naar postvakken van gebruikers in uw Microsoft 365 organisatie. Veritas biedt u [](https://globanet.com/pivot/) een draailijnconnector die is geconfigureerd om items uit de gegevensbron van derden vast te leggen (op regelmatige basis) en deze items vervolgens te importeren in Microsoft 365. Pivot is een chatplatform waarmee kan worden samengewerkt met deelnemers aan de financiële markt. De verbindingslijn converteert items zoals chatberichten, van de pivot-accounts van een gebruiker naar een e-mailberichtindeling en importeert deze items vervolgens in de postvakken van gebruikers in Microsoft 365.

Nadat draaitabelgegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance. Als u een pivot-verbindingslijn gebruikt om gegevens te importeren en te archiveren in Microsoft 365 kan uw organisatie voldoen aan het overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-pivot-data"></a>Overzicht van het archiveren van draaitabelgegevens

In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn voor het archiveren van de draaitabelgegevens in Microsoft 365.

![Archiveringswerkstroom voor draaitabelgegevens](../media/PivotConnectorWorkflow.png)

1. Uw organisatie werkt samen met Pivot om een pivotbronsite in te stellen en te configureren.

2. Eens in de 24 uur worden draaititems gekopieerd naar de Veritas Merge1-site. De verbindingslijn converteert ook de draaititems naar een e-mailberichtindeling.

3. De draaipuntconnector die u maakt in het Microsoft 365 compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en draagt de draaititems over naar een veilige Azure Storage-locatie in de Microsoft-cloud.

4. De verbindingslijn importeert de draaititems naar de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in [stap 3.](#step-3-map-users-and-complete-the-connector-setup) Er wordt een submap in de map Postvak IN met de naam **Pivot** gemaakt in de postvakken van de gebruiker en de items worden geïmporteerd in die map. De verbindingslijn doet dit met behulp van de waarde van de eigenschap *E-mail.* Elk draaitabelitem bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer aan het item.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Veritas Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://www.veritas.com/content/support/)om dit account te maken. U meld u aan bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de draailijnconnector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina Gegevensconnectors in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-pivot-connector"></a>Stap 1: De pivot-verbindingslijn instellen

De eerste stap is toegang tot de pagina Gegevensconnectoren in het Microsoft-compliancecentrum en het maken van een **verbindingslijn** voor draaigegevens.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectors**  >  **Pivot**.

2. Klik op **de pagina Productbeschrijving** van draaipunt op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-pivot-connector-on-the-veritas-merge1-site"></a>Stap 2: De draailijnconnector configureren op de Veritas Merge1-site

De tweede stap is het configureren van de pivot-verbindingslijn op de site Samenvoegen1. Zie Gebruikershandleiding voor [connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf)van derden samenvoegen voor informatie over het configureren van de draailijnconnector op de site Veritas Merge1.

Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard verbindingslijn in het Microsoft 365 compliancecentrum weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de connector wilt voltooien in het Microsoft 356-compliancecentrum, volgt u de volgende stappen:

1. Schakel automatische **gebruikerstoewijzing** in op de pagina Microsoft 365 gebruikers toewijzen. De draaititems bevatten een eigenschap met de naam *E-mail,* die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** bekijk uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-pivot-connector"></a>Stap 4: De pivot-verbindingslijn controleren

Nadat u de pivot-verbindingslijn hebt maakt, kunt u de status van de verbindingslijn bekijken in het Microsoft 365 compliancecentrum.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de **draailijnconnector** om de flyoutpagina weer te geven. Deze pagina bevat de eigenschappen en informatie over de verbindingslijn.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.