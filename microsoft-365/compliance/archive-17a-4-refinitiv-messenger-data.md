---
title: Een connector instellen voor het archiveren van Refinitiv Eikon Messenger-gegevens in Microsoft 365
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
description: Meer informatie over het instellen en gebruiken van een Refinitiv Eikon Messenger DataParser-connector van 17a-4 om Refinitiv Eikon Messenger-gegevens te importeren en te archiveren in Microsoft 365.
ms.openlocfilehash: 59380695a6ade9a7dfc36c51ea4254e13a7fd03c
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097109"
---
# <a name="set-up-a-connector-to-archive-refinitiv-eikon-messenger-data-preview"></a>Een connector instellen voor het archiveren van Refinitiv Eikon Messenger-gegevens (voorbeeld)

Gebruik [de Refinitiv Eikon Messenger DataParser](https://www.17a-4.com/refinitiv-messenger-dataparser/) van 17a-4 LLC om gegevens uit Refinitiv Eikon Messenger te importeren en te archiveren naar postvakken van gebruikers in uw Microsoft 365 organisatie. De DataParser bevat een Refinitiv Eikon Messenger-connector die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365. De Refinitiv Eikon Messenger DataParser-connector converteert Refinitiv Eikon Messenger-gegevens naar een e-mailberichtindeling en importeert deze items vervolgens in gebruikerspostvakken in Microsoft 365.

Nadat Refinitiv Eikon Messenger-gegevens zijn opgeslagen in postvakken van gebruikers, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance. Met een Refinitiv Eikon Messenger-connector voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-refinitiv-eikon-messenger-data"></a>Overzicht van het archiveren van Refinitiv Eikon Messenger-gegevens

In het volgende overzicht wordt uitgelegd hoe u een gegevensconnector gebruikt om Refinitiv Eikon Messenger-gegevens te archiveren in Microsoft 365.

![Archiveringswerkstroom voor Refinitiv Eikon Messenger-gegevens van 17a-4](../media/RefinitivMessengerDataParserConnectorWorkflow.png)

1. Uw organisatie werkt met 17a-4 om de Refinitiv Eikon Messenger DataParser in te stellen en te configureren.

2. Regelmatig worden Refinitiv Eikon Messenger-items verzameld door de DataParser. De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.

3. De Refinitiv Eikon Messenger DataParser-connector die u in de Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en brengt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.

4. Een submap in de map Postvak IN met de naam **Refinitiv Eikon Messenger DataParser** wordt gemaakt in de postvakken van de gebruiker en de Refinitiv Eikon Messenger-items worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk Refinitiv Eikon Messenger-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

- Maak een DataParser-account voor Microsoft-connectors. Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/) U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de Refinitiv Eikon Messenger DataParser-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-a-refinitiv-eikon-messenger-dataparser-connector"></a>Stap 1: Een Refinitiv Eikon Messenger DataParser-connector instellen

De eerste stap is om toegang te krijgen tot de pagina Gegevensconnectors in de Microsoft 365-compliancecentrum en een 17a-4-connector te maken voor Refinitiv Eikon Messenger-gegevens.

1. Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren**  >  **Refinitiv Eikon Messenger DataParser**.

2. Klik op **de pagina Productbeschrijving van Refinitiv Eikon Messenger DataParser** op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw 17a-4-account en voltooi de stappen in de wizard Refinitiv Eikon Messenger DataParser-verbinding.

## <a name="step-2-configure-the-refinitiv-eikon-messenger-dataparser-connector"></a>Stap 2: De Refinitiv Eikon Messenger DataParser-connector configureren

Werk met 17a-4 Ondersteuning om de Refinitiv Eikon Messenger DataParser-connector te configureren.

## <a name="step-3-map-users"></a>Stap 3: Gebruikers in kaart brengen

De Refinitiv Eikon Messenger DataParser-connector zal gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.

## <a name="step-4-monitor-the-refinitiv-eikon-messenger-dataparser-connector"></a>Stap 4: De Refinitiv Eikon Messenger DataParser-connector controleren

Nadat u een Refinitiv Eikon Messenger DataParser-connector hebt aan Microsoft 365-compliancecentrum.

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op het tabblad **Connectors** en selecteer vervolgens de Refinitiv Eikon Messenger DataParser-connector die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.
