---
title: Een Connector voor gegevensparser van Deymfonie instellen voor het archiveren van gegevens in Microsoft 365
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
description: Meer informatie over het instellen en gebruiken van een 17a-4 Symphony DataParser-connector voor het importeren en archiveren van gegevens van Den Microsoft 365.
ms.openlocfilehash: da947c80a296aa4fee8ccabb9bb82eecc1d9b103
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096974"
---
# <a name="set-up-a-connector-to-archive-symphony-data-preview"></a>Een verbindingslijn instellen voor het archiveren van Gegevens van Dessymfonie (voorbeeld)

Gebruik de [Symphony DataParser](https://www.17a-4.com/Symphony-dataparser/) van 17a-4 LLC om communicatiegegevens van Den 17a-4 te importeren en te archiveren in postvakken van gebruikers in uw Microsoft 365 organisatie. De DataParser bevat een Connector van Deymfonie die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365. Met de Connector Gegevensparser van Symphony worden de Gegevensparser-gegevens van Deymfonie ge converteert naar een e-mailberichtindeling en worden deze items vervolgens geïmporteerd in postvakken van gebruikers in Microsoft 365.

Nadat De gegevens van Symphony zijn opgeslagen in postvakken van gebruikers, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance. Met behulp van een Connector voor Het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-symphony-data"></a>Overzicht van het archiveren van De gegevens van Dessymfonie

In het volgende overzicht wordt uitgelegd hoe het gebruik van een gegevensconnector wordt gebruikt voor het archiveren van Gegevens van Deymfonie in Microsoft 365.

![Archiving workflow for Symphony data from 17a-4](../media/SymphonyDataParserConnectorWorkflow.png)

1. Uw organisatie werkt samen met 17a-4 om de Gegevensparser van De symfonie in te stellen en te configureren.

2. Op regelmatige basis worden De items van de symfonie verzameld door de DataParser. De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.

3. De Connector Gegevensparser van Deymfonie die u in de Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en brengt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.

4. Er wordt een submap gemaakt in de map Postvak IN met de naam **Symphony DataParser** in de postvakken van de gebruiker en de Items van Dessymfonie worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk Item van de symfonie bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

- Maak een DataParser-account voor Microsoft-connectors. Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/) U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de Connector Voor het importeren van postvak maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-a-symphony-dataparser-connector"></a>Stap 1: Een Connector voor gegevensparser van Dessymfonie instellen

De eerste stap is om toegang te krijgen tot de pagina Gegevensconnectors in de Microsoft 365-compliancecentrum en een 17a-4-connector te maken voor De gegevens van Deymfonie.

1. Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectors**  >  **Symphony DataParser**.

2. Klik op de pagina Productbeschrijving van De beschrijving **van Deymfoniegegevensparser** op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw 17a-4-account en voltooi de stappen in de wizard Gegevensparser-verbinding van De symfonie.

## <a name="step-2-configure-the-symphony-dataparser-connector"></a>Stap 2: De Connector Voor gegevensparser configureren

Werk met ondersteuning voor 17a-4 om de Connector Voor Gegevensparser van De symfonie te configureren.

## <a name="step-3-map-users"></a>Stap 3: Gebruikers in kaart brengen

Met de Connector Gegevensparser van Symphony worden gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.

## <a name="step-4-monitor-the-symphony-dataparser-connector"></a>Stap 4: De Connector Voor de gegevensparser van Dessymfonie controleren

Nadat u een Connector Voor Gegevensparser hebt aangemaakt, kunt u de verbindingslijnstatus in de Microsoft 365-compliancecentrum.

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de Connector Voor gegevensparser van Dessymfonie die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.
