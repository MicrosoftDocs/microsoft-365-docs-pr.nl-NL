---
title: Een verbindingslijn instellen voor het archiveren van gegevens met tekst in Microsoft 365
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
description: Beheerders kunnen een verbindingslijn instellen voor het importeren en archiveren van gegevens met tekst van Veritas in Microsoft 365. Met deze connector kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365. Nadat u deze gegevens hebt gearchiveerd, kunt u compliancefuncties, zoals juridische bewaring, inhoudszoekbeleid en bewaarbeleid, gebruiken om gegevens van derden te beheren.
ms.openlocfilehash: 9a8265766dd08a78c3f218710a3bc4b623f7f670
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162308"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a>Een verbindingslijn instellen voor het archiveren van gegevens met tekst

Gebruik een Veritas-verbindingslijn in het Microsoft 365 compliancecentrum om tekst met scheidingstekens te importeren en te archiveren in gebruikerspostvakken in uw Microsoft 365 organisatie. Veritas biedt [](https://globanet.com/text-delimited) een verbindingslijn met tekst die is geconfigureerd om items uit een externe gegevensbron vast te leggen (op regelmatige basis) en deze items te importeren in Microsoft 365. De verbindingslijn converteert inhoud van de gegevensbron met tekst naar een e-mailberichtindeling en importeert deze items vervolgens in het postvak van de gebruiker in Microsoft 365.

Nadat gegevens met tekst zijn opgeslagen in postvakken van gebruikers, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery en bewaarbeleid en bewaarlabels. Als u een gegevensconnector met tekst scheidingstekens gebruikt om gegevens te importeren en te archiveren in Microsoft 365 kan uw organisatie voldoen aan het overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-the-text-delimited-data"></a>Overzicht van het archiveren van de gegevens met tekstde scheidingstekens

In het volgende overzicht wordt uitgelegd hoe u een verbindingslijn gebruikt om brongegevens met tekst te archiveren in Microsoft 365.

![Archiveringswerkstroom voor gegevens met tekst](../media/TextDelimitedConnectorWorkflow.png)

1. Uw organisatie werkt met de bron met tekstde scheidingstekens om een site met tekst te configureren en te configureren.

2. Eens in de 24 uur worden chatberichten uit de bron met tekst scheidingstekens gekopieerd naar de Veritas Merge1-site. De verbindingslijn converteert ook de inhoud naar een e-mailberichtindeling.

3. De verbindingslijn met tekst die u in het Microsoft 365-compliancecentrum maakt, maakt elke dag verbinding met de Veritas Merge1-site en brengt de berichten over naar een veilige Azure Storage-locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde berichtitems naar de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in stap 3. Er wordt een nieuwe submap gemaakt in de map Postvak IN met de naam **Tekst-** Scheidingstekens in de postvakken van de gebruiker en de berichtitems worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk bericht bevat deze eigenschap, die wordt ingevuld met het e-mailadres van elke deelnemer.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Veritas Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://globanet.com/ms-connectors-contact)om dit account te maken. U meld u aan bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de verbindingslijn met tekst in stap 1 maakt (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-the-text-delimited-connector"></a>Stap 1: de verbindingslijn met tekst scheidingstekens instellen

De eerste stap is om toegang te krijgen tot de pagina Gegevensconnectoren in het Microsoft 365 compliancecentrum en een **verbindingslijn** te maken voor gegevens met tekst.scheidingstekens.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectoren**  >  **Tekst-scheidingstekens**.

2. Klik op **de pagina productbeschrijving** met tekst scheidingstekens op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-the-text-delimited-connector-on-the-veritas-merge1-site"></a>Stap 2: De verbindingslijn met tekst met scheidingstekens configureren op de Veritas Merge1-site

De tweede stap is het configureren van de verbindingslijn met tekst die is scheidingstekens op de site Samenvoegen1. Zie Handleiding Verbindingslijnen van derden samenvoegen voor informatie over het configureren van de [verbindingslijn](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf)met tekst die is scheidingstekens op de site Veritas Samenvoegen1.

Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard verbindingslijn in het Microsoft 365 compliancecentrum weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

Als u gebruikers wilt in kaart brengen en de configuratie van de verbindingslijn wilt voltooien in het Microsoft 365 compliancecentrum, volgt u de volgende stappen:

1. Schakel op **de pagina Externe gebruikers toewijzen Microsoft 365 gebruikers in,** automatische gebruikerstoewijzing in. De bronitems met tekst- scheidingstekens bevatten een eigenschap *met* de naam E-mail, die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

2. Klik **op Volgende,** controleer uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-text-delimited-connector"></a>Stap 4: De verbindingslijn met tekstde scheidingstekens controleren

Nadat u de verbindingslijn Tekst- scheidingstekens hebt maken, kunt u de verbindingslijnstatus weergeven in het Microsoft 365 compliancecentrum.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de **verbindingslijn Tekst- scheidingstekens** om de flyoutpagina weer te geven. Deze pagina bevat de eigenschappen en informatie over de verbindingslijn.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat informatie over de gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.