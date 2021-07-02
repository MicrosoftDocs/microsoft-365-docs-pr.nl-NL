---
title: Documenten exporteren naar het account van uw Azure Storage organisatie
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-mar2020
description: Exporteert documenten in een revisieset naar een Azure Storage account en gebruik Azure Storage Explorer om ze te downloaden naar een lokale computer.
ms.openlocfilehash: b7638e33a40a2ac46f4bb69b869e4c2cf6d48f65
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256505"
---
# <a name="export-documents-in-a-review-set-to-an-azure-storage-account"></a>Documenten in een revisieset exporteren naar een Azure Storage account

Wanneer u documenten exporteert uit een revisieset in een Advanced eDiscovery, hebt u de optie om ze te exporteren naar een Azure Storage account dat door uw organisatie wordt beheerd. Als u deze optie gebruikt, worden de documenten geüpload naar uw Azure Storage locatie. Nadat ze zijn geëxporteerd, kunt u de documenten openen (en downloaden naar een lokale computer of andere locatie) met behulp van de Azure Storage Explorer. In dit artikel vindt u instructies voor het exporteren van documenten naar uw Azure Storage-account en het gebruik van de Azure Storage Explorer om verbinding te maken met een Azure Storage locatie om de geëxporteerde documenten te downloaden. Zie Gebruik Azure Storage Explorer voor [meer Azure Storage Explorer.](/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)

## <a name="before-you-export-documents-from-a-review-set"></a>Voordat u documenten exporteert uit een revisieset

- U moet een SAS-token (Shared Access Signature) opgeven voor uw Azure Storage-account en de URL voor een specifieke container in het opslagaccount om documenten uit een revisieset te exporteren. Zorg ervoor dat u deze bij de hand hebt (bijvoorbeeld gekopieerd naar een tekstbestand) wanneer u stap 2 uit te voeren

  - **SAS-token:** Zorg ervoor dat u het SAS-token krijgt voor uw Azure Storage account (en niet voor de container). U kunt een SAS-token voor uw account genereren in Azure Storage. Hiervoor gaat u naar het Azure Storage account en selecteert u  **Toegangshandtekening** delen onder de Instellingen instellingen in het opslagaccountblad. Gebruik de standaardinstellingen en sta alle resourcetypen toe wanneer u het SAS-token genereert.

  - **Container-URL:** u moet een container maken om de documenten van de revisieset te uploaden naar en vervolgens een kopie van de URL voor de container krijgen. `https://ediscoverydata.blob.core.windows.net/exportdata`bijvoorbeeld. Als u de URL wilt krijgen, gaat u naar de container in Azure Storage en **selecteert** u Eigenschappen onder de **Instellingen** sectie in het containerblad.

- Download en installeer de Azure Storage Explorer. Zie het Azure Storage Explorer [voor instructies.](https://go.microsoft.com/fwlink/p/?LinkId=544842) U gebruikt dit hulpprogramma om verbinding te maken met de container in Azure Storage account en de documenten te downloaden die u hebt geëxporteerd in stap 1.

## <a name="step-1-export-the-documents-from-a-review-set"></a>Stap 1: De documenten exporteren uit een revisieset

De eerste stap is het maken van een exportklus om documenten uit een revisieset te exporteren. Zie Documenten exporteren uit een revisieset voor meer gedetailleerde instructies over alle [exportopties.](export-documents-from-review-set.md) In de volgende procedure worden de instellingen belicht voor het exporteren van documenten naar het account Azure Storage uw organisatie.

1. Open in Microsoft 365-compliancecentrum het hoofd- Advanced eDiscovery, selecteer  het tabblad Revisiesets en selecteer vervolgens de revisieset die u wilt exporteren.

2. Klik in de revisieset op **Actie**  >  **exporteren.**

3. Typ op **de flyoutpagina** Exportopties een naam (vereist) en beschrijving (optioneel) voor de export.

4. Configureer de instellingen in de secties documenten, metagegevens, inhoud en opties. Zie Documenten exporteren uit een revisieset voor meer informatie over [deze instellingen.](export-documents-from-review-set.md)

5. Selecteer in **de sectie Uitvoeropties** de **optie Gecondenseerde** adreslijststructuur die naar uw Azure Storage account wordt geëxporteerd.

6. Plak de container-URL en het SAS-token voor uw opslagaccount in de bijbehorende velden.

   ![De verbindings-URL en het SAS-token in de bijbehorende velden plakken](../media/AzureStorageOutputOptions.png)

7. Klik **op Exporteren** om de exportklus te maken.

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>Stap 2: De SAS-URL van de exportklus verkrijgen

De volgende stap is het verkrijgen van de SAS-URL die wordt gegenereerd nadat u de exportklus hebt gemaakt in stap 1. U gebruikt de SAS-URL om verbinding te maken met de container in uw Azure Storage account waar u de revisiesetdocumenten naar hebt geëxporteerd.

1. Ga op **Advanced eDiscovery** pagina naar de zaak en klik vervolgens op **het tabblad** Exporteren.

2. Klik op **het** tabblad Export op de exportklus die u wilt downloaden. Dit is de exportklus die u hebt gemaakt in stap 1.

3. Kopieer op de flyoutpagina onder **Locaties** de SAS-URL die wordt weergegeven. Zo nodig kunt u het bestand opslaan in een tekstbestand, zodat u het in stap 3 kunt openen.

   ![De SAS-URL kopiëren die wordt weergegeven onder Locaties](../media/eDiscoExportJob.png)

   > [!TIP]
   > De SAS-URL die wordt weergegeven in de exportklus is een samenvoeging van de CONTAINER-URL en het SAS-token voor uw Azure Storage account. U kunt deze kopiëren vanuit de exportklus of zelf maken door de URL en het SAS-token te combineren.

## <a name="step-3-connect-to-the-azure-storage-container"></a>Stap 3: Verbinding maken naar de Azure Storage container

De laatste stap is om de Azure Storage Explorer en de SAS-URL te gebruiken om verbinding te maken met de container in uw Azure Storage-account en de geëxporteerde documenten naar een lokale computer te downloaden.

1. Start de Azure Storage Explorer die u hebt gedownload en geïnstalleerd.

2. Klik op **het pictogram Verbinding maken dialoogvenster** openen.

   ![Klik op het pictogram Account toevoegen](../media/AzureStorageConnect.png)

3. Klik op **Verbinding maken pagina Azure Storage** op Blob **container.**

4. Selecteer op **de pagina Verificatiemethode** selecteren de optie **Sas (Shared Access signature)** en klik vervolgens op **Volgende**.

5. Plak op **de pagina Verbindingsgegevens** invoeren de SAS-URL (die u hebt verkregen in de exportklus in stap 2) in het vak **Blob Container SAS URL.**

    ![De SAS-URL in het vak URI plakken](../media/AzureStorageConnect3.png)

    U ziet dat de containernaam wordt weergegeven in het **vak Weergavenaam.** U kunt deze naam bewerken.

6. Klik **op Volgende** om de **overzichtspagina weer te** geven en klik vervolgens op **Verbinding maken.**

    Het **knooppunt blobcontainers** **(onder Storage Accounts**  >  **(Bijgevoegde containers)** wordt \> geopend.

    ![Taken exporteren in het knooppunt Blobs containers](../media/AzureStorageConnect5.png)

    De container bevat een container met de weergavenaam uit stap 5. Deze container bevat een map voor elke exportklus die u hebt gedownload naar de container in uw Azure Storage account. Deze mappen worden benoemd met een id die overeenkomt met de id van de exportklus. U kunt deze export-ID's (en de  naam van de export) vinden onder Ondersteuningsinformatie op  de flyoutpagina voor elke voorbereiding van gegevens voor **exporttaken** die worden weergegeven op het tabblad Taken in het Advanced eDiscovery geval.

7. Dubbelklik op de exportmap om deze te openen.

   Er wordt een lijst met mappen en exportrapporten weergegeven.

    ![De exportmap bevat geëxporteerde bestanden en exportrapporten](../media/AzureStorageConnect6.png)

8. Als u alle inhoud van de  exportklus wilt exporteren, klikt u op de pijl-omhoog om terug te gaan naar de map Exportklus en klikt u vervolgens op **Downloaden.**

9. Geef de locatie op waar u de geëxporteerde bestanden wilt downloaden en klik vervolgens op Map selecteren.

    Met Azure Storage Explorer start u het downloadproces. De status van het downloaden van de geëxporteerde items wordt weergegeven in het **deelvenster** Activiteiten. Er wordt een bericht weergegeven wanneer de download is voltooid.

> [!NOTE]
> In plaats van de hele exportklus in Azure Storage Explorer downloaden, kunt u specifieke items selecteren die u wilt downloaden en weergeven.

## <a name="more-information"></a>Meer informatie

- De map Taak exporteren bevat de volgende items. De werkelijke items in de exportmap worden bepaald door de exportopties die zijn geconfigureerd toen de exportklus werd gemaakt. Zie Documenten exporteren uit een revisieset voor meer informatie over [deze opties.](export-documents-from-review-set.md)

  - Export_load_file.csv: Dit CSV-bestand is een detailexportrapport met informatie over elk geëxporteerd document. Het bestand bestaat uit een kolom voor elke eigenschap metagegevens voor een document. Zie de kolom Geëxporteerde veldnaam in de tabel  in documentmetagegevensvelden in Advanced eDiscovery voor een lijst en beschrijving van de metagegevens die in dit [rapport zijn opgenomen.](document-metadata-fields-in-advanced-ediscovery.md)

  - Summary.txt: Een tekstbestand met een overzicht van de export, inclusief exportstatistieken.

  - Extracted_text_files: Deze map bevat een tekstbestandsversie van elk geëxporteerd document.

  - NativeFiles: Deze map bevat een oorspronkelijke bestandsversie van elk geëxporteerd document.

  - Error_files: Deze map bevat de volgende items wanneer de exportklus foutbestanden bevat:

    - ExtractionError.csv: Dit CSV-bestand bevat de beschikbare metagegevens voor bestanden die niet correct zijn geëxtraheerd uit het bovenliggende item.

    - ProcessingError: Deze map bevat documenten met verwerkingsfouten. Deze inhoud is op itemniveau, wat betekent dat als een bijlage een verwerkingsfout heeft, het document met de bijlage ook in deze map wordt opgenomen.
