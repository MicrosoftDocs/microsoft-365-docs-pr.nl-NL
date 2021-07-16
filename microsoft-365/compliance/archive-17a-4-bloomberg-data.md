---
title: Een verbindingslijn instellen voor het archiveren van Gegevens van Bloomberg in Microsoft 365
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
description: Meer informatie over het instellen en gebruiken van een 17a-4 Bloomberg DataParser-connector voor het importeren en archiveren van Gegevensparser-gegevens in Microsoft 365.
ms.openlocfilehash: 2d4005468d7df7987d1794e8d61262c8fde70b5f
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454539"
---
# <a name="set-up-a-connector-to-archive-bloomberg-data"></a>Een verbindingslijn instellen voor het archiveren van Gegevens van Bloomberg

Gebruik de [Gegevensparser van](https://www.17a-4.com/Bloomberg-dataparser/) 17a-4 LLC van Bloomberg om gegevens uit Bloomberg te importeren en te archiveren in postvakken van gebruikers in uw Microsoft 365 organisatie. De DataParser bevat een Connector van Bloomberg die is geconfigureerd om items uit een externe gegevensbron vast te leggen en deze items te importeren in Microsoft 365. Met de Connector DataParser van Bloomberg worden Gegevensparser-gegevens ge converteert naar een e-mailberichtindeling en worden deze items vervolgens geïmporteerd in postvakken van gebruikers in Microsoft 365.

Nadat Gegevens van Bloomberg zijn opgeslagen in postvakken van gebruikers, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery, bewaarbeleid en bewaarlabels en communicatie compliance. Als u een Connector van Bloomberg gebruikt om gegevens te importeren en te archiveren in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-bloomberg-data"></a>Overzicht van het archiveren van Gegevens van Bloomberg

In het volgende overzicht wordt uitgelegd hoe het gebruik van een gegevensconnector voor het archiveren van Gegevensgegevens in een Microsoft 365.

![Archiveringswerkstroom voor Gegevens van Bloomberg van 17a-4](../media/BloombergDataParserConnectorWorkflow.png)

1. Uw organisatie werkt met 17a-4 om de Gegevensparser van Bloomberg in te stellen en te configureren.

2. Op regelmatige basis worden De artikelen van Bloomberg verzameld door de DataParser. De Gegevensparser converteert ook de inhoud van een bericht naar een e-mailberichtindeling.

3. De Gegevensparser-connector van Bloomberg die u in de Microsoft 365-compliancecentrum maakt, maakt verbinding met DataParser en brengt de berichten over naar een veilige Azure Storage locatie in de Microsoft-cloud.

4. Een submap in de map Postvak IN met de naam **Bloomberg DataParser** wordt gemaakt in de postvakken van de gebruiker en de Items van Bloomberg worden geïmporteerd in die map. De verbindingslijn bepaalt in welk postvak items moeten worden geïmporteerd met behulp van de waarde van de eigenschap *E-mail.* Elk Bloomberg-item bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer.

## <a name="before-you-set-up-a-connector"></a>Voordat u een verbindingslijn in stelt

- Maak een DataParser-account voor Microsoft-connectors. Neem hiervoor contact op [met 17a-4 LLC.](https://www.17a-4.com/contact/) U moet zich aanmelden bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de Connector Gegevensparser van Bloomberg maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in de Microsoft 365-compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-a-bloomberg-dataparser-connector"></a>Stap 1: Een DataParser-connector voor Bloomberg instellen

De eerste stap is toegang tot de pagina Gegevensconnectoren in de Microsoft 365-compliancecentrum en een 17a-4-connector voor Gegevens van Bloomberg te maken.

1. Ga naar <https://compliance.microsoft.com> en klik vervolgens op Data **connectors**  >  **Bloomberg DataParser**.

2. Klik op de pagina Productbeschrijving van **Bloomberg DataParser** op **Verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw 17a-4-account en voltooi de stappen in de verbindingswizard van Bloomberg DataParser.

## <a name="step-2-configure-the-bloomberg-dataparser-connector"></a>Stap 2: De DataParser-connector van Bloomberg configureren

Werk met 17a-4 Ondersteuning om de DataParser-connector van Bloomberg te configureren.

## <a name="step-3-map-users"></a>Stap 3: Gebruikers in kaart brengen

De Gegevensparser-connector van Bloomberg zal gebruikers automatisch aan hun e-mailadressen Microsoft 365 voordat ze gegevens importeren in Microsoft 365.

## <a name="step-4-monitor-the-bloomberg-dataparser-connector"></a>Stap 4: De DataParser-connector van Bloomberg controleren

Nadat u een DataParser-verbindingslijn voor Bloomberg hebt aan Microsoft 365-compliancecentrum.

1. Ga naar <https://compliance.microsoft.com> en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Connectors** en selecteer vervolgens de Verbindingslijn met Gegevensparser van Bloomberg die u hebt gemaakt om de flyoutpagina weer te geven, die de eigenschappen en informatie over de verbindingslijn bevat.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.
