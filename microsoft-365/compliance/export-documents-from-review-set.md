---
title: Documenten exporteren vanuit een controleset
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
ms.assetid: ''
description: Informatie over het selecteren en exporteren van inhoud uit een Advanced eDiscovery voor presentaties of externe beoordelingen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "52162570"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Documenten exporteren uit een revisieset in Advanced eDiscovery

Met Exporteren kunnen gebruikers de inhoud aanpassen die is opgenomen in het downloadpakket wanneer u een document exporteert vanuit een revisieset in Advanced eDiscovery.

Documenten exporteren uit een revisieset:

1. Open in Microsoft 365 compliancecentrum het hoofd- Advanced eDiscovery, selecteer  het tabblad Revisiesets en selecteer vervolgens de revisieset die u wilt exporteren.

2. Klik in de revisieset op **Actie**  >  **exporteren.**

   Met het hulpmiddel Exporteren wordt de flyoutpagina weergegeven met de instellingen voor het configureren van de export. Sommige opties zijn standaard geselecteerd, maar u kunt deze wijzigen. Zie de volgende sectie voor beschrijvingen van de exportopties die u kunt configureren.

   ![Configuratieopties voor het exporteren van items uit een revisieset](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. Nadat u de export hebt geconfigureerd, klikt u **op Exporteren om** het exportproces te starten. Afhankelijk van de optie die u **hebt** geselecteerd in de sectie Uitvoeropties, kunt u de exportbestanden openen via direct downloaden of in het account van Azure Storage organisatie.

> [!NOTE]
> Exporttaken blijven behouden voor de levensduur van de zaak. U moet de inhoud van een exportklus echter binnen 30 dagen nadat de exportklus is voltooid, downloaden.

## <a name="export-options"></a>Exportopties

Gebruik de volgende opties om de export te configureren.

- **Exportnaam:** naam van de exportklus.

- **Beschrijving**: Veld Vrije tekst om een beschrijving toe te voegen.

- **Deze documenten exporteren**

  - **Alleen geselecteerde documenten:** deze optie exporteert alleen de documenten die momenteel zijn geselecteerd.
  
  - **Alle documenten in de revisieset:** met deze optie worden alle documenten in de revisieset geexporteert.

- **Metagegevens**
  
  - **Bestand laden:** dit bestand bevat metagegevens voor elk bestand. Dit bestand kan meestal worden ingenomen door eDiscovery-hulpprogramma's van derden. Zie Metagegevensvelden in documenten [in](document-metadata-fields-in-Advanced-eDiscovery.md)Advanced eDiscovery.
  
  - **Tags:** Wanneer u deze optie hebt geselecteerd, wordt labelingsgegevens opgenomen in het laadbestand.

- **Content**
  
  - **Oorspronkelijke bestanden:** Schakel dit selectievakje in om de oorspronkelijke bestanden van de documenten in de revisieset op te nemen. Als u ervoor kiest om native bestanden te exporteren, hebt u de volgende opties voor het exporteren van chatgesprekken.
  
  - **Gespreksopties**

    - **Gespreksbestanden:** Deze optie exporteert gereconstrueerde chatgesprekken. Deze indeling bevat gesprekken in een formulier dat lijkt op wat gebruikers zien in de oorspronkelijke toepassing.

    - **Afzonderlijke chatberichten:** met deze optie worden de oorspronkelijke gespreksbestanden opgeslagen in Microsoft 365.

- **Opties**

  - **Tekstbestanden:**- Deze optie bevat de uitgepakte tekstversies van oorspronkelijke bestanden in de export.
  
  - **Redacted natives vervangen** door geconverteerde PDF-bestanden: als er tijdens de revisie opnieuw uitgevoerde PDF-bestanden worden gegenereerd, zijn deze bestanden beschikbaar voor export. U kunt ervoor kiezen om alleen de oorspronkelijke bestanden te exporteren die opnieuw zijn uitgevoerd (door deze optie niet te selecteren) of u kunt deze optie selecteren om de PDF-bestanden te exporteren die de werkelijke redactions bevatten.

- **Uitvoeropties:** Geëxporteerde inhoud kan rechtstreeks via een webbrowser worden gedownload of kan worden verzonden naar een Azure Storage account. Met de eerste twee opties kunt u direct downloaden.
  
  - **Losse bestanden en PST's**(e-mail wordt indien mogelijk toegevoegd aan PST's) : Bestanden worden geëxporteerd in een indeling die lijkt op de oorspronkelijke adreslijststructuur die gebruikers in hun eigen toepassingen zien.  Zie de sectie Losse bestanden en [PST-exportstructuur voor meer](#loose-files-and-pst-export-structure) informatie.
  
  - **Gecondenseerde** adreslijststructuur: Bestanden worden geëxporteerd en opgenomen in de download.
  
  - **Gecondenseerde** adreslijststructuur geëxporteerd naar uw Azure Storage account: Bestanden worden geëxporteerd naar het account Azure Storage uw organisatie. Voor deze optie moet u de URL opgeven voor de container in Azure Storage account om de bestanden naar te exporteren. U moet ook het SAS-token (Shared Access Signature) voor uw Azure Storage geven. Zie Documenten exporteren in een revisieset naar een Azure Storage [account voor meer informatie.](download-export-jobs.md)

In de volgende secties wordt de mapstructuur voor losse bestanden en de opties voor een verkorte adreslijststructuur beschreven.

### <a name="loose-files-and-pst-export-structure"></a>Losse bestanden en PST-exportstructuur

Als u deze exportoptie selecteert, is de geëxporteerde inhoud ingedeeld in de volgende structuur:

- Hoofdmap: Deze map in benoemde ExportName.zip
  
  - Export_load_file.csv: Het metagegevensbestand.
  
  - Summary.csv: Een overzichtsbestand dat ook exportstatistieken bevat.
  
  - Exchange: Deze map bevat alle inhoud van Exchange in de oorspronkelijke bestandsindeling. Natives-bestanden worden vervangen door ge redacted PDF's als u de optie **Redacted Natives** vervangen door geconverteerde PDF's hebt geselecteerd.
  
  - SharePoint: Deze map bevat alle oorspronkelijke inhoud van SharePoint in een oorspronkelijke bestandsindeling. Natives-bestanden worden vervangen door ge redacted PDF's als u de optie **Redacted Natives** vervangen door geconverteerde PDF's hebt geselecteerd.

### <a name="condensed-directory-structure"></a>Gecondenseerde adreslijststructuur

- Hoofdmap: Deze map heeft de naam ExportName.zip
  
  - Export_load_file.csv: Het metagegevensbestand.
  
  - Summary.txt: Een overzichtsbestand dat ook exportstatistieken bevat.
  
  - NativeFiles: Deze map bevat alle oorspronkelijke bestanden die zijn geëxporteerd. Als u opnieuw uitgevoerde PDF-bestanden exporteert, worden deze niet in PST-bestanden gezet. In plaats daarvan worden ze toegevoegd aan een gescheiden map.
  
  - Error_files: Deze map bevat de volgende foutbestanden, als deze zijn opgenomen in de export:

    - ExtractieFout: een CSV-bestand dat alle beschikbare metagegevens bevat van bestanden die niet correct zijn geëxtraheerd uit bovenliggende bestanden.

    - ProcessingError: Dit bestand bevat een lijst met documenten met verwerkingsfouten. Deze inhoud is itemniveau, wat betekent dat als een bijlage een verwerkingsfout heeft veroorzaakt, het e-mailbericht met de bijlage in deze map wordt opgenomen.
  
  - Extracted_text_files: Deze map bevat alle uitgepakte tekstbestanden die tijdens de verwerking zijn gegenereerd.
