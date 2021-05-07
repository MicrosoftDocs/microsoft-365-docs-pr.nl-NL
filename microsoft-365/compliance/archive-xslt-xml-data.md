---
title: Een verbindingslijn instellen voor het archiveren van XSLT/XML-gegevens in Microsoft 365
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
description: Beheerders kunnen een connector instellen voor het importeren en archiveren van XSLT/XML-gegevens van Veritas in Microsoft 365. Met deze verbindingslijn kunt u gegevens van externe gegevensbronnen archiveren in Microsoft 365, zodat u compliancefuncties zoals juridische bewaring, inhoud zoeken en bewaarbeleid kunt gebruiken om de gegevens van derden van uw organisatie te beheren.
ms.openlocfilehash: 51b05f83c51626bc60dc19b5ec9a63750903281c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162302"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>Een connector instellen voor het archiveren van XSLT/XML-gegevens

Gebruik een Veritas-connector in het Microsoft 365 compliancecentrum om gegevens uit de webpaginabron te importeren en te archiveren in gebruikerspostvakken in uw Microsoft 365 organisatie. Veritas biedt u een [XSLT/XML-connector](https://globanet.com/xslt-xml) waarmee u snel bestanden kunt ontwikkelen die zijn gemaakt met behulp van XSLT (Extensible Style sheet Language Transformations) om XML-bestanden om te zetten in andere bestandsindelingen (zoals HTML of tekst) die kunnen worden geïmporteerd in Microsoft 365. De connector converteert de inhoud van een item uit de XSLT/XML-bron naar een e-mailberichtindeling en importeert vervolgens het geconverteerd item naar Microsoft 365 postvakken.

Nadat XSLT/XML-gegevens zijn opgeslagen in gebruikerspostvakken, kunt u Microsoft 365 compliancefuncties toepassen, zoals Litigation Hold, eDiscovery en bewaarbeleid en bewaarlabels. Met een XSLT/XML-connector voor het importeren en archiveren van gegevens in Microsoft 365 kan uw organisatie voldoen aan overheids- en regelgevingsbeleid.

## <a name="overview-of-archiving-xsltxml-data"></a>Overzicht van het archiveren van XSLT/XML-gegevens

In het volgende overzicht wordt uitgelegd hoe het gebruik van een verbindingslijn voor het archiveren van XSLT/XML-brongegevens in Microsoft 365.

![Archiveringswerkstroom voor XSLT/XML-gegevens](../media/XSLT-XMLConnectorWorkflow.png)

1. Uw organisatie werkt met de XSLT/XML-bron om een XSLT/XML-site in te stellen en te configureren.

2. Eens in de 24 uur worden chatberichten uit de XSLT/XML-bron gekopieerd naar de Veritas Merge1-site. De verbindingslijn converteert ook de inhoud naar een e-mailberichtindeling.

3. De XSLT/XML-connector die u maakt in het Microsoft 365-compliancecentrum, maakt elke dag verbinding met de Veritas Merge1-site en draagt de berichten over naar een veilige Azure Storage-locatie in de Microsoft-cloud.

4. De connector importeert de geconverteerde berichtitems naar de postvakken van specifieke gebruikers met behulp van de waarde van de eigenschap *E-mail* van de automatische gebruikerstoewijzing, zoals beschreven in stap 3. Er wordt een nieuwe submap in de map Postvak IN met de naam **XSLT/XML** gemaakt in de postvakken van de gebruiker en de berichtitems worden geïmporteerd in die map. De verbindingslijn doet dit met behulp van de waarde van de eigenschap *E-mail.* Elk bericht bevat deze eigenschap, die wordt gevuld met het e-mailadres van elke deelnemer van het bericht.

## <a name="before-you-begin"></a>Voordat u begint

- Maak een Veritas Merge1-account voor Microsoft-connectors. Neem contact op met [Veritas Customer Support](https://www.veritas.com/content/support/)om dit account te maken. U meld u aan bij dit account wanneer u de verbindingslijn maakt in stap 1.

- De gebruiker die de XSLT/XML-connector maakt in stap 1 (en deze voltooit in stap 3), moet worden toegewezen aan de rol Postvak importeren exporteren in Exchange Online. Deze rol is vereist om verbindingslijnen toe te voegen op de pagina **Gegevensconnectors** in het Microsoft 365 compliancecentrum. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer in Exchange Online. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren toewijzen en vervolgens de juiste gebruikers toevoegen als leden. Zie de secties [](/Exchange/permissions-exo/role-groups#create-role-groups) Rollengroepen [](/Exchange/permissions-exo/role-groups#modify-role-groups) maken of Rollengroepen wijzigen in het artikel 'Rollengroepen beheren in Exchange Online'.

## <a name="step-1-set-up-an-xsltxml-connector"></a>Stap 1: Een XSLT/XML-connector instellen

De eerste stap is toegang tot de gegevensconnectors in het Microsoft 365 compliancecentrum en een **verbindingslijn** maken voor XSLT/XML-gegevens.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com/) en klik vervolgens op **Gegevensconnectors**  >  **XSLT/XML.**

2. Klik op **de pagina XSLT/XML-productbeschrijving** op **Nieuwe verbindingslijn toevoegen.**

3. Klik op **de pagina Servicevoorwaarden** op **Accepteren.**

4. Voer een unieke naam in die de verbindingslijn identificeert en klik vervolgens op **Volgende.**

5. Meld u aan bij uw Merge1-account om de verbindingslijn te configureren.

## <a name="step-2-configure-an-xsltxml-connector"></a>Stap 2: Een XSLT/XML-connector configureren

De tweede stap is het configureren van de XSLT/XML-connector op de merge1-site. Zie Handleiding [Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)van derden samenvoegen voor informatie over het configureren van de XSLT/XML-connector op de site Veritas Samenvoegen1.

Nadat u op **Opslaan &** Voltooien  hebt geklikt, wordt de pagina Gebruikerstoewijzing in de wizard verbindingslijn in het Microsoft 365 compliancecentrum weergegeven.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Stap 3: Gebruikers in kaart brengen en de configuratie van de connector voltooien

1. Als u gebruikers wilt in kaart brengen en de configuratie van de verbindingslijn wilt voltooien in het Microsoft 365 compliancecentrum, volgt u de onderstaande stappen:

2. Schakel op **de pagina XSLT/XML-gebruikers** toewijzen Microsoft 365 gebruikers automatisch toewijzen in. De XSLT/XML-items bevatten een eigenschap *met* de naam E-mail, die e-mailadressen bevat voor gebruikers in uw organisatie. Als de verbindingslijn dit adres kan koppelen aan Microsoft 365 gebruiker, worden de items geïmporteerd in het postvak van die gebruiker.

3. Klik **op Volgende,** bekijk uw instellingen en ga naar de pagina Gegevensconnectors om de voortgang van het importproces voor de nieuwe **verbindingslijn** te bekijken.

## <a name="step-4-monitor-the-xsltxml-connector"></a>Stap 4: De XSLT/XML-connector controleren

Nadat u de XSLT/XML-verbindingslijn hebt gebruikt, kunt u de verbindingslijnstatus weergeven in het Microsoft 365 compliancecentrum.

1. Ga naar [https://compliance.microsoft.com](https://compliance.microsoft.com) en klik op **Gegevensconnectoren** in het linkernavigatievenster.

2. Klik op **het tabblad Verbindingslijnen** en selecteer vervolgens de **XSLT/XML-connector** om de flyoutpagina weer te geven. Deze pagina bevat de eigenschappen en informatie over de verbindingslijn.

3. Klik **onder Verbindingsstatus met bron** op de koppeling Logboek **downloaden** om het statuslogboek voor de verbindingslijn te openen (of op te slaan). Dit logboek bevat gegevens die zijn geïmporteerd in de Microsoft-cloud.

## <a name="known-issues"></a>Bekende problemen

- Op dit moment bieden we geen ondersteuning voor het importeren van bijlagen of items die groter zijn dan 10 MB. Ondersteuning voor grotere items is op een later tijdstip beschikbaar.