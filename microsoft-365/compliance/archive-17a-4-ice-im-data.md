---
title: Een connector instellen voor het archiveren van ICE-Verbinding maken Chatgegevens in Microsoft 365
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
description: Meer informatie over het instellen en gebruiken van een ICE-Verbinding maken 17a-4 Ice Verbinding maken Chat DataParser-connector voor het importeren en archiveren van ICE-Verbinding maken Chatgegevens in Microsoft 365.
ms.openlocfilehash: 0aac5c701f122eaf99497635281ebc07d835fc2e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454479"
---
# <a name="set-up-a-connector-to-archive-ice-connect-chat-data"></a>Een connector instellen voor het archiveren van ICE-Verbinding maken Chatgegevens

Gebruik ICE [DataParser](https://www.17a-4.com/ice-dataparser/) van 17a-4 LLC om gegevens uit ICE Verbinding maken Chat te importeren en te archiveren in postvakken van gebruikers in uw Microsoft 365 organisatie. De DataParser bevat een ICE Chat-connector die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365. De ICE DataParser-connector converteert ICE-Verbinding maken Chatgegevens naar een e-mailberichtindeling en importeert deze items vervolgens in gebruikerspostvakken in Microsoft 365.

Nadat ICE Verbinding maken Chatgegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance. Als u een ICE DataParser-connector gebruikt voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-ice-chat-data"></a>Overzicht van het archiveren van ICE Chat-gegevens

In het volgende overzicht wordt uitgelegd hoe u een gegevensconnector gebruikt om ICE-Verbinding maken chatgegevens te archiveren in Microsoft 365.

![Archiveringswerkstroom voor ICE Verbinding maken Chatgegevens van 17a-4](../media/ICEChatDataParserConnectorWorkflow.png)

1. Uw organisatie werkt met 17a-4 om ICE DataParser in te stellen en te configureren.

2. Ice-Verbinding maken chatitems worden regelmatig verzameld door de DataParser. De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.

3. De ICE DataParser-connector die u in de Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en brengt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.

4. Er wordt een submap gemaakt in de map Postvak IN met de naam **ICE DataParser** in de postvakken van de gebruiker en de ICE Verbinding maken Chat-items worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk ICE Verbinding maken Chatitem bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

- Maak een DataParser-account voor Microsoft-connectors. Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/) U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de ICE DataParser-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-an-ice-dataparser-connector"></a>Stap 1: Een ICE DataParser-connector instellen

De eerste stap is om toegang te krijgen tot de pagina Gegevensconnectors in de Microsoft 365-compliancecentrum en een 17a-4-connector te maken voor ICE-Verbinding maken Chatgegevens.

1. Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren**  >  **ICE DataParser**.

2. Klik op **de pagina ICE DataParser-productbeschrijving** op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw 17a-4-account en voltooi de stappen in de wizard ICE DataParser-verbinding.

## <a name="step-2-configure-the-ice-dataparser-connector"></a>Stap 2: De ICE DataParser-connector configureren

Werk met 17a-4 Ondersteuning om de ICE DataParser-connector te configureren.

## <a name="step-3-map-users"></a>Stap 3: Gebruikers in kaart brengen

De ICE DataParser-connector zal gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.

## <a name="step-4-monitor-the-ice-dataparser-connector"></a>Stap 4: De ICE DataParser-connector controleren

Nadat u een ICE DataParser-verbindingslijn hebt aan Microsoft 365-compliancecentrum.

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Connectors** en selecteer vervolgens de ICE DataParser-connector die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.
