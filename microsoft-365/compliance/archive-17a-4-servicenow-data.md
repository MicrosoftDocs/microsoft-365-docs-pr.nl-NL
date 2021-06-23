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
description: Meer informatie over het instellen en gebruiken van een 17a-4 ServiceNow DataParser-connector voor het importeren en archiveren van ServiceNow-gegevens in Microsoft 365.
ms.openlocfilehash: 9faa5fb1bf03bb7ab1e97b0bbd24aad4c38e91ae
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096967"
---
# <a name="set-up-a-connector-to-archive-servicenow-data-preview"></a>Een connector instellen voor het archiveren van ServiceNow-gegevens (voorbeeld)

Gebruik [serviceNow DataParser](https://www.17a-4.com/dataparser/) van 17a-4 LLC om gegevens uit ServiceNow te importeren en te archiveren in gebruikerspostvakken in uw Microsoft 365 organisatie. De DataParser bevat een ServiceNow-connector die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365. De ServiceNow DataParser-connector converteert ServiceNow-gegevens naar een e-mailberichtindeling en importeert deze items vervolgens in gebruikerspostvakken in Microsoft 365.

Nadat ServiceNow-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance. Als u een ServiceNow-connector gebruikt voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-servicenow-data"></a>Overzicht van het archiveren van ServiceNow-gegevens

In het volgende overzicht wordt uitgelegd hoe u een gegevensconnector gebruikt om ServiceNow-gegevens te archiveren in Microsoft 365.

![Archiveringswerkstroom voor ServiceNow-gegevens van 17a-4](../media/ServiceNowDataParserConnectorWorkflow.png)

1. Uw organisatie werkt met 17a-4 om de ServiceNow DataParser in te stellen en te configureren.

2. Op regelmatige basis worden ServiceNow-items verzameld door de DataParser. De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.

3. De ServiceNow DataParser-connector die u in de Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en draagt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.

4. Een submap in de map Postvak IN met de naam **ServiceNow DataParser** wordt gemaakt in de postvakken van gebruikers en de ServiceNow-items worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk ServiceNow-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

- Maak een DataParser-account voor Microsoft-connectors. Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/) U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de ServiceNow DataParser-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-a-servicenow-dataparser-connector"></a>Stap 1: Een ServiceNow DataParser-connector instellen

De eerste stap is toegang tot de pagina Gegevensconnectoren in de Microsoft 365-compliancecentrum en een 17a-4-connector voor ServiceNow-gegevens te maken.

1. Ga naar <https://compliance.microsoft.com> en klik vervolgens op **Gegevensconnectoren**  >  **ServiceNow DataParser**.

2. Klik op **de pagina ServiceNow DataParser** productbeschrijving op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw 17a-4-account en voltooi de stappen in de wizard ServiceNow DataParser-verbinding.

## <a name="step-2-configure-the-servicenow-dataparser-connector"></a>Stap 2: De ServiceNow DataParser-connector configureren

Werk met 17a-4 Ondersteuning om de ServiceNow DataParser-connector te configureren.

## <a name="step-3-map-users"></a>Stap 3: Gebruikers in kaart brengen

De ServiceNow DataParser-connector zal gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.

## <a name="step-4-monitor-the-servicenow-dataparser-connector"></a>Stap 4: De ServiceNow DataParser-connector controleren

Nadat u een ServiceNow DataParser-verbindingslijn hebt aan Microsoft 365-compliancecentrum.

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op het tabblad **Verbindingslijnen** en selecteer vervolgens de ServiceNow DataParser-connector die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.
