---
title: Uploaden via het netwerk gebruiken om de PST-bestanden van uw organisatie te importeren
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 'Voor beheerders: informatie over uploaden via het netwerk om meerdere PST-bestanden bulksgewijs te importeren in gebruikerspostvakken in Microsoft 365.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6ff645589337260cd8e29d1e1d066abdf60c1f1a
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280919"
---
# <a name="use-network-upload-to-import-your-organizations-pst-files-to-microsoft-365"></a>Gebruik uploaden via het netwerk om de PST-bestanden van uw organisatie te importeren in Microsoft 365

> [!NOTE]
> Dit artikel is bedoeld voor beheerders. Probeert u PST-bestanden te importeren in uw eigen postvak? Zie [E-mail, contactpersonen en agenda importeren uit een .pst-bestand van Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075).
  
Hier zijn de stapsgewijze instructies voor uploaden via het netwerk om meerdere PST-bestanden bulksgewijs te importeren in Microsoft 365-postvakken. Zie [Veelgestelde vragen voor uploaden via het netwerk om PST-bestanden te importeren](./faqimporting-pst-files-to-office-365.yml#using-network-upload-to-import-pst-files) voor veelgestelde vragen over uploaden via het netwerk om PST-bestanden bulksgewijs te importeren in Microsoft 365.
  
[Stap 1: kopieer de SAS-URL en installeer AzCopy](#step-1-copy-the-sas-url-and-install-azcopy)

[Stap 2: upload uw PST-bestanden naar Microsoft 365](#step-2-upload-your-pst-files-to-office-365)

[(Optioneel) Stap 3: bekijk een lijst van de geüploade PST-bestanden](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Stap 4: maak het toewijzingsbestand voor de PST-import](#step-4-create-the-pst-import-mapping-file)

[Stap 5: maak een PST-importtaak](#step-5-create-a-pst-import-job)

[Stap 6: filter gegevens en start de PST-importtaak](#step-6-filter-data-and-start-the-pst-import-job)

U hoeft stap 1 slechts eenmaal uit te voeren om PST-bestanden te importeren in Microsoft 365-postvakken. Nadat u deze stap hebt uitgevoerd, voert u stappen 2 tot en met 6 uit telkens wanneer u een batch met PST-bestanden wilt uploaden en importeren.

## <a name="before-you-import-pst-files"></a>Voordat u PST-bestanden importeert
  
- U moet de rol Postvak importeren exporteren toegewezen krijgen in Exchange Online om PST-bestanden te kunnen importeren in Microsoft 365-postvakken. Deze rol is standaard niet toegewezen aan een rollengroep in Exchange Online. U kunt de rol Postvak importeren exporteren toevoegen aan de rollengroep Organisatiebeheer. U kunt ook een rollengroep maken, de rol Postvak importeren exporteren daar aan toewijzen, en uzelf als lid toevoegen. Zie de gedeelten Een rol aan een rollengroep toevoegen of Een rollengroep maken in [Rollengroepen beheren](/Exchange/permissions-exo/role-groups) voor meer informatie.

    Als u importtaken wilt maken in het beveiligings- en compliancecentrum, moet bovendien sprake zijn van een van de volgende gevallen:

  - De rol van e-mailgeadresseerde moet aan u zijn toegewezen in Exchange Online. Deze rol wordt standaard toegewezen aan de rollengroepen Organisatiebeheer en Recipient Management.

    Of

  - U moet ook globale beheerder zijn in uw organisatie.

  > [!TIP]
    > U zou een nieuwe rollengroep kunnen maken in Exchange Online die speciaal is bedoeld voor het importeren van PST-bestanden. Wijs de rollen Postvak importeren exporteren en E-mailgeadresserde toe aan de nieuwe rollengroep en voeg er vervolgens leden aan toe voor het minimale niveau van machtigingen die zijn vereist voor het importeren van PST-bestanden.
  
- De enige ondersteunde methode voor het importeren van PST-bestanden in Microsoft 365 is het hulpprogramma AzCopy, zoals beschreven in dit onderwerp. U kunt Azure Storage Explorer niet gebruiken om PST-bestanden rechtstreeks naar het Azure Storage-gebied te uploaden.

- U moet de PST-bestanden die u wilt importeren in Microsoft 365 opslaan op een bestandsserver of in een gedeelde map binnen uw organisatie. In stap 2 voert u het hulpprogramma AzCopy uit waarmee u de PST-bestanden, die zijn opgeslagen op de bestandsserver of in de gedeelde map, uploadt naar Microsoft 365.

- Grote PST-bestanden beïnvloeden mogelijk de prestaties van het PST-importproces. Het is dus raadzaam dat elk PST-bestand dat u uploadt naar de Azure-opslaglocatie in stap 2 kleiner is dan 20 GB.

- Deze procedure bestaat uit het kopiëren en opslaan van een URL die een toegangssleutel bevat. Die informatie wordt in stap 2 gebruikt voor het uploaden van uw PST-bestanden, en in stap 3 als u een lijst wilt weergeven met de PST-bestanden die zijn geüpload naar Office 365. Neem maatregelen ter bescherming van deze URL, net zoals voor het beschermen van wachtwoorden of andere beveiligingsinformatie. U kunt de URL bijvoorbeeld opslaan in een met een wachtwoord beveiligd Microsoft Word-document of op een versleuteld USB-station. Zie de sectie [Meer informatie](#more-information) voor een voorbeeld van deze gecombineerde URL en sleutel.

- U kunt PST-bestanden importeren in een inactief postvak in Office 365. U kunt dit doen door de GUID van het inactieve postvak op te geven in de `Mailbox`-parameter in het toewijzingsbestand van de PST-import. Zie stap 4 op het tabblad **Instructies** in dit onderwerp voor meer informatie. 

- In een hybride Exchange-implementatie kunt u PST-bestanden importeren in een archiefpostvak in de cloud voor een gebruiker waarvan het primaire postvak zich on-premises bevindt. Daarvoor doet u het volgende in het toewijzingsbestand voor de PST-import:

  - Geef het e-mailadres op van het on-premises postvak van de gebruiker in de parameter `Mailbox`.

  - Geef de waarde **WAAR** op in de parameter `IsArchive`.

    Zie [stap 4](#step-4-create-the-pst-import-mapping-file) voor meer informatie.

- Nadat PST-bestanden zijn geïmporteerd, wordt de instelling Blokkeren voor bewaren van het postvak voor onbepaalde tijd ingeschakeld. Dit houdt in dat het bewaarbeleid dat is toegepast op het postvak niet wordt verwerkt totdat u de blokkering opheft of een datum opgeeft waarop de blokkering wordt opgeheven. Waarom doen we dit? Als berichten die u importeert in een postvak oud zijn, zouden ze permanent kunnen worden verwijderd als de bewaarperiode, die is geconfigureerd in de instellingen van het bewaarbeleid van het postvak, is verstreken. Door het postvak te blokkeren voor bewaren, heeft de eigenaar de gelegenheid de geïmporteerde berichten te beheren. Daarnaast hebt u de gelegenheid om de instellingen van het bewaarbeleid van het postvak te wijzigen. Zie het gedeelte [Meer informatie](#more-information) in dit onderwerp voor suggesties voor het beheren van het blokkeren voor bewaren.

- Standaard is de maximale berichtgrootte die kan worden ontvangen door een Microsoft 365-postvak 35 MB. Dat komt omdat de standaardwaarde voor de eigenschap *MaxReceiveSize* voor een postvak is ingesteld op 35 MB. De limiet voor de maximale grootte van het te ontvangen bericht in Microsoft 365 is echter 150 MB. Dus als u een PST-bestand importeert dat een item bevat dat groter is dan 35 MB, wordt door de Office 365-importservice de waarde van de eigenschap *MaxReceiveSize* van het doelpostvak automatisch gewijzigd in 150 MB. Hierdoor kunnen berichten van maximaal 150 MB worden geïmporteerd in postvakken van gebruikers.

    > [!TIP]
    > U kunt deze opdracht uitvoeren in Exchange Online PowerShell om de grootte van het ontvangen bericht van het postvak vast te stellen:  `Get-Mailbox <user mailbox> | FL MaxReceiveSize`.

- Zie het gedeelte [Hoe het importproces werkt](#how-the-import-process-works) in dit artikel voor een overzicht van het PST-importproces.

## <a name="step-1-copy-the-sas-url-and-install-azcopy"></a>Stap 1: kopieer de SAS-URL en installeer AzCopy

De eerste stap is het downloaden en installeren van het hulpprogramma AzCopy, dat u in stap 2 nodig hebt om PST-bestanden te uploaden naar Office 365. Ook kopieert u de SAS-URL voor uw organisatie. Deze URL is een combinatie van de netwerk-URL van de Azure-opslaglocatie in de Microsoft-cloud voor uw organisatie, en een SAS-sleutel (Shared Access Signature). Deze sleutel biedt u de machtigingen die u nodig hebt voor het uploaden van PST-bestanden naar uw Azure-opslaglocatie. Neem maatregelen ter bescherming van de SAS-URL. Deze is uniek voor uw organisatie en wordt gebruikt in stap 2.

> [!IMPORTANT]
> Als u PST-bestanden wilt importeren via de methode uploaden via het netwerk en de opdrachtsyntaxis die in dit artikel wordt beschreven, moet u de versie van AzCopy gebruiken die kan worden gedownload in stap 6b in de volgende procedure. U kunt ook [hier](https://aka.ms/downloadazcopy) dezelfde versie van AzCopy downloaden. Het gebruik van een andere versie van AzCopy wordt niet ondersteund.
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met de referenties van een beheerdersaccount in uw organisatie.

2. In het linkerdeelvenster van het beveiligings- en compliancecentrum klikt u op **Informatiebeheer** \> **Importeren** \> **PST-bestanden importeren**.

    > [!NOTE]
    > U moet de juiste machtigingen bezitten om de pagina **Importeren** te kunnen openen in het beveiligings- en compliancecentrum. Zie het gedeelte **Voordat u begint** voor meer informatie. 

3. Klik op de pagina **PST-bestanden importeren** op ![Pictogram toevoegen](../media/ITPro-EAC-AddIcon.gif) **Nieuwe importtaak**.

    De wizard voor het maken van een importtaak wordt weergegeven.

4. Typ een naam voor de PST-importtaak en klik op **Volgende**. U kunt kleine letters, getallen, streepjes en onderstrepingstekens gebruiken. U kunt geen hoofdletters of spaties in de naam gebruiken.

5. Op de pagina **Wilt u gegevens uploaden of verzenden?** klikt u op **Uw gegevens uploaden** en vervolgens op **Volgende**.

    ![Klikken op Uw gegevens uploaden om een importtaak voor het uploaden via het netwerk te maken](../media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. Doe op de pagina **Gegevens importeren** de volgende twee dingen:

    ![Kopieer de SAS-URL en download het hulpprogramma AzCopy op de pagina Gegevens importeren](../media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    1. Klik in stap 2 op **SAS-URL voor netwerkupload weergeven**. Nadat de SAS-URL wordt weergegeven, klikt u op **Kopiëren naar klembord** en plakt u het in een bestand dat u opslaat, zodat u het later kunt openen.

    2. In stap 3 klikt u op **Azure AzCopy downloaden** om het hulpprogramma AzCopy te downloaden en te installeren. Klik in het pop-upvenster op **Uitvoeren** om AzCopy te installeren.

   > [!NOTE]
   > U kunt de pagina **Gegevens importeren** openhouden (voor het geval u de SAS-URL opnieuw moet kopiëren) of op **Annuleren** klikken om de pagina te sluiten. 

## <a name="step-2-upload-your-pst-files-to-office-365"></a>Stap 2: upload uw PST-bestanden naar Office 365

U kunt nu het hulpprogramma AzCopy.exe gebruiken om PST-bestanden te uploaden naar Office 365. Het hulpprogramma uploadt de PST-bestanden en slaat ze op in een Azure-opslaglocatie in de Microsoft-cloud. Zoals eerder aangegeven, bevindt de Azure-opslaglocatie waarnaar u uw PST-bestanden uploadt zich in hetzelfde regionale Microsoft-datacenter als waar uw organisatie zich bevindt. Om deze stap te kunnen voltooien moeten de PST-bestanden zich bevinden in een bestandsshare of op een bestandsserver in uw organisatie. Dit heet de bronmap in deze procedure. Elke keer dat u het hulpprogramma AzCopy uitvoert, kunt u een andere bronmap opgeven.

> [!NOTE]
> Zoals eerder aangegeven mag geen enkel PST-bestand dat u uploadt naar de Azure-opslaglocatie groter zijn dan 20 GB. PST-bestanden die groter zijn dan 20 GB, beïnvloeden mogelijk de prestaties van het PST-importproces dat u start in stap 6. Bovendien moet elk PST-bestand een unieke naam hebben.

1. Open een opdrachtprompt op uw lokale computer.

2. Ga naar de map waarin u AzCopy.exe hebt geïnstalleerd in stap 1. Als u het hulpprogramma hebt geïnstalleerd in de standaardlocatie, gaat u naar `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`.

3. Voer de volgende opdracht uit om de PST-bestanden te uploaden naar Office 365.

    ```powershell
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
    ```

    > [!IMPORTANT]
    > U moet een map opgeven als bronlocatie in de vorige opdracht, u kunt geen individueel PST-bestand opgeven. Alle PST-bestanden in de bronmap worden geüpload.

    In de volgende tabel worden de parameters en de vereiste waarden van AzCopy.exe beschreven. De gegevens die u hebt verkregen in de vorige stap, worden gebruikt in de waarden voor deze parameters.

    | Parameter | Beschrijving | Voorbeeld |
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Hiermee geeft u de bronmap in uw organisatie op die de PST-bestanden bevat die u gaat uploaden naar Office 365.  <br/> De waarde van deze parameter moet tussen dubbele aanhalingstekens (“ ”) staan.  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |Hiermee geeft u de SAS-URL op die u hebt verkregen in stap 1.  <br/> De waarde van deze parameter moet tussen dubbele aanhalingstekens (“ ”) staan.<br/><br/>**Opmerking:** Als u de SAS-URL gebruikt in een script of batchbestand moet u oppassen voor bepaalde tekens die moeten worden geïdentificeerd met een escape-teken. U moet bijvoorbeeld `%` veranderen in `%%` en `&` in `^&`.<br/><br/>**Tip:** (optioneel) U kunt een submap opgeven in de Azure-opslaglocatie waarnaar u de PST-bestanden wilt uploaden. U doet dit door de locatie van een submap toe te voegen (na ‘ingestiondata’) in de SAS-URL. In het eerst voorbeeld wordt geen submap opgegeven. Dat betekent dat de PST-bestanden worden geüpload naar de hoofdmap (genaamd *ingestiondata*) van de Azure-opslaglocatie. In het tweede voorbeeld worden de PST-bestanden geüpload naar een submap (genaamd *PSTFiles*) in de hoofdmap van de Azure-opslaglocatie.  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> Of  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |Hiermee worden uitgebreide statusberichten in een logbestand opgeslagen. Standaard heeft het logbestand de naam AzCopyVerbose.log en bevindt het zich in %LocalAppData%\Microsoft\Azure\AzCopy. Als u een bestaande bestandslocatie voor deze optie opgeeft, wordt het uitgebreide logboek toegevoegd aan dat bestand.  <br/> De waarde van deze parameter moet tussen dubbele aanhalingstekens (“ ”) staan.  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |Deze optionele schakeloptie schakelt de recursieve modus in, waardoor het hulpprogramma AzCopy ook PST-bestanden kopieert die zich bevinden in submappen van de bronmap die u hebt opgegeven met de `/Source:`-parameter.  <br/> **Opmerking:** Als u deze schakeloptie gebruikt, hebben de PST-bestanden een ander bestandspad in de Azure-opslaglocatie nadat ze zijn geüpload. U moet de exacte naam van het pad naar de bestanden opgeven in het CSV-bestand dat u maakt in stap 4.  <br/> | `/S` <br/> |
    | `/Y` <br/> |Met deze vereiste schakeloptie kunt u SAS-tokens voor alleen-schrijven gebruiken wanneer u de PST-bestanden uploadt naar de Azure-opslaglocatie. De SAS-URL die u in stap 1 hebt opgehaald (en opgegeven in parameter `/Dest:`) is een alleen-schrijven-SAS-URL en daarom moet u deze schakeloptie opnemen. Met een alleen-schrijven-SAS-URL kunt u toch Azure Storage Explorer gebruiken om een lijst met PST-bestanden te bekijken die zijn geüpload naar de Azure-opslaglocatie.  <br/> | `/Y` <br/> |

Hier volgt een voorbeeld van de syntaxis voor het hulpprogramma AzCopy.exe, waarbij daadwerkelijke waarden voor elke parameter worden gebruikt:

```powershell
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
```

Nadat u de opdracht uitvoert, worden statusberichten weergegeven die de voortgang van het uploaden van de PST-bestanden weergeven. Een laatste statusbericht geeft het aantal bestanden weer dat is geüpload.

> [!TIP]
> Nadat u de opdracht AzCopy.exe hebt uitgevoerd en hebt gecontroleerd dat alle parameters juist zijn, slaat u een kopie van de opdrachtregelsyntaxis op in hetzelfde (beveiligde) bestand als waarin u de informatie uit stap 1 hebt opgeslagen. Daarna kunt u deze informatie kopiëren en plakken in een opdrachtprompt elke keer wanneer u het hulpprogramma AzCopy.exe uitvoert om PST-bestanden te uploaden naar Office 365. De enige waarden die u mogelijk moet wijzigen zijn die voor de parameter `/Source:`. Dit is afhankelijk van de bronmap waarin de PST-bestanden zich bevinden.

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Stap 3 (optioneel): bekijk de lijst met PST-bestanden die zijn geüpload naar Office 365

U kunt eventueel de Microsoft Azure Storage Explorer (een gratis open-sourcehulpprogramma) installeren en gebruiken om een lijst weer te geven met de PST-bestanden die u hebt geüpload naar de Azure-blob. Er zijn twee goede redenen om dit te doen:
  
- Om te controleren dat de PST-bestanden uit de gedeelde map of van de bestandsserver in uw organisatie zijn geüpload naar de Azure-blob.

- Om te controleren of de bestandsnaam (en de naam van het pad van de submap, indien aanwezig) klopt voor elke PST-bestand dat u hebt geüpload naar de Azure-blob. Dit is handig wanneer u het PST-toewijzingsbestand maakt in de volgende stap, omdat u de naam van het pad naar zowel de map als het bestand moet opgeven voor elk PST-bestand. Door deze namen te controleren voorkomt u mogelijke fouten in uw PST-toewijzingsbestand.

De zelfstandige Azure Storage Explorer-toepassing is algemeen beschikbaar. U kunt de meest recente versie downloaden via de koppeling in de volgende procedure.
  
> [!IMPORTANT]
> U kunt Azure Storage Explorer niet gebruiken om PST-bestanden te uploaden of wijzigen. De enige ondersteunde methode voor het importeren van PST-bestanden is het gebruik van AzCopy. U kunt ook geen PST-bestanden verwijderen die u hebt geüpload in de Azure-blob. Als u een PST-bestand wilt verwijderen, krijgt u een foutbericht met de mededeling dat u niet over de vereiste machtigingen beschikt. Houd er rekening mee dat alle PST-bestanden automatisch uit het Azure-opslaggebied worden verwijderd. Als er geen importtaken aan de gang zijn, worden alle PST-bestanden in de **ingestiondata**-container 30 dagen nadat de laatste importtaak is gemaakt, verwijderd.
  
Ga als volgt te werk om de Azure Storage Explorer te installeren en verbinding te maken met uw Azure-opslaglocatie:
  
1. Download en installeer het [hulpprogramma Microsoft Azure Storage Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842).

2. Start Microsoft Azure Storage Explorer.

3. Klik op de pagina **Bron selecteren**, in het dialoogvenster **Verbinding maken met Azure Storage** op **Blob-container**.
  
4. Selecteer op de pagina **Verificatiemethode selecteren** de optie **SAS-handtekening (Shared Access Signature)** en klik dan op **Volgende**.

5. Plak op de pagina **Verbindingsgegevens invoeren** in het vak onder **Blob-container SAS-URL** de SAS-URL die u in stap 1 hebt opgehaald en klik dan op **Volgende**. Nadat u de SAS-URL hebt geplakt, wordt het vak onder **Weergavenaam** automatisch gevuld met **ingestiondata**.

6. Op de pagina **Overzicht** kunt u de verbindingsinformatie bekijken. Klik vervolgens op **Verbinden**.

    De container **ingestiondata** wordt geopend. De container bevat de PST-bestanden die u in stap 2 hebt geüpload. De container **ingestiondata** bevindt zich onder **Storage-accounts** \> **(Bijgesloten containers)** \> **Blob-containers**. 
  
7. Als u klaar bent met het gebruik van de Microsoft Azure Storage Explorer klikt u met de rechtermuisknop op **ingestiondata** en vervolgens op **Ontkoppelen** om de verbinding met uw Azure-opslaglocatie te verbreken. Als u dat niet doet, wordt er een foutbericht weergegeven wanneer u de volgende keer probeert de koppeling te maken.
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>Stap 4: maak het toewijzingsbestand voor de PST-import

Nadat u de PST-bestanden hebt geüpload naar de Azure-opslaglocatie voor uw organisatie, is de volgende stap het maken van een bestand met door komma’s gescheiden waarden (CSV), waarin u opgeeft in welke gebruikerspostvakken de PST-bestanden moeten worden geïmporteerd. Dit CSV-bestand dient u in bij de volgende stap, wanneer u een PST-importtaak maakt.
  
1. [Download een exemplaar van het toewijzingsbestand voor de PST-import](https://go.microsoft.com/fwlink/p/?LinkId=544717).

2. Open het CSV-bestand of sla het op uw lokale computer op. Hieronder staat een voorbeeld van een ingevuld toewijzingsbestand voor PST-import, dat is geopend in Kladblok. Het is veel makkelijker om Microsoft Excel te gebruiken om het CSV-bestand te bewerken.

    ```console
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,PSTFiles,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,PSTFiles,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    De eerste rij, ofwel de veldnamenrij, van het CSV-bestand bevat de parameters die worden gebruikt door de PST-importservice voor het importeren van de PST-bestanden in gebruikerspostvakken. De namen van parameters worden gescheiden door een komma. Elke rij onder de veldnamenrij bevat de parameterwaarden voor het importeren van een PST-bestand in een specifiek postvak. U hebt een rij nodig voor elk PST-bestand dat u wilt importeren in een gebruikerspostvak. Er kunnen maximaal 500 rijen in het CSV-toewijzingsbestand. Om meer dan 500 PST-bestanden te importeren, hebt u meerdere toewijzingsbestanden nodig en moet u meerdere importtaken maken in stap 5.

    > [!NOTE]
    > Verander niets in de veldnamenrij, ook niet de SharePoint-parameters. Deze worden genegeerd tijdens het PST-importproces. Vergeet ook niet de tijdelijke gegevens in het toewijzingsbestand te vervangen door de werkelijke gegevens.

3. U kunt de informatie in de volgende tabel gebruiken om het CSV-bestand te vullen met de benodigde informatie.

    | Parameter | Beschrijving | Voorbeeld |
    |:-----|:-----|:-----|
    | `Workload` <br/> |Hiermee geeft u de service op waarin de gegevens worden geïmporteerd. Gebruik `Exchange` om PST-bestanden te importeren in gebruikerspostvakken.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Hiermee geeft u de locatie van de map in de Azure-opslaglocatie op waarnaar u de PST-bestanden hebt geüpload in stap 2.  <br/> Als u in stap 2 geen optionele submap in de SAS-URL hebt opgegeven in de parameter `/Dest:`, kunt u deze parameter leeg laten in het CSV-bestand. Als u wel een submap hebt toegevoegd, geeft u die op in deze parameter (zie het tweede voorbeeld). Deze parameterwaarde is hoofdlettergevoelig.  <br/> U moet in *geen* geval ‘ingestiondata’ opnemen in de waarde voor de parameter `FilePath`.  <br/><br/> **Belangrijk:** De hoofdletters en kleine letters in de naam van het pad naar het bestand moeten identiek zijn als u in stap 2 een optionele naam van een submap in de SAS-URL hebt opgenomen in de parameter `/Dest:`. Als u bijvoorbeeld `PSTFiles` hebt gebruikt als naam van de submap in stap 2 en vervolgens `pstfiles` gebruikt in de parameter `FilePath` in het CSV-bestand, mislukt het importeren van het PST-bestand. Zorg dat u in beide gevallen dezelfde hoofdletters en kleine letters gebruikt.  <br/> |(laat leeg)  <br/> Of  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |Hiermee geeft u de naam op van het PST-bestand dat u wilt importeren in het gebruikerspostvak. Deze parameterwaarde is hoofdlettergevoelig. De bestandsnaam voor elk PST-bestand in het toewijzingsbestand voor een importtaak moet uniek zijn. <br/> <br/>**Belangrijk:** De hoofdletters en kleine letters in de naam van het PST-bestand in het CSV-bestand moeten identiek zijn aan die van het PST-bestand dat u in stap 2 hebt geüpload naar de Azure-opslaglocatie. Als u bijvoorbeeld `annb.pst` gebruikt in de parameter`Name` in het CSV-bestand, maar de naam PST-bestand in werkelijkheid `AnnB.pst` is, mislukt het importeren van dat PST-bestand. Zorg dat u in de naam van het PST-bestand in het CVS-bestand dezelfde hoofdletters en kleine letters gebruikt als in de daadwerkelijke naam van het PST-bestand.  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |Hiermee geeft u het e-mailadres op van het postvak waarin u het PST-bestand gaat importeren. U kunt geen openbare map opgeven omdat de PST-importservice geen ondersteuning biedt voor het importeren van PST-bestanden in openbare mappen.  <br/> Als u een PST-bestand wilt importeren in een inactief postvak, moet u de postvak-GUID voor deze parameter opgeven. Om deze GUID te verkrijgen voert u de volgende PowerShell-opdracht uit in Exchange Online: `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**Opmerking:** Soms zijn er mogelijk meerdere postvakken met hetzelfde e-mailadres, waarbij het ene postvak actief is en het andere voorlopig verwijderd (of inactief) is. In die situatie moet u de postvak-GUID opgeven als unieke aanduiding van het postvak waarin u het PST-bestand wilt importeren. Om deze GUID te verkrijgen voor actieve postvakken voert u de volgende PowerShell-opdracht uit: `Get-Mailbox <identity of active mailbox> | FL Guid`. Om de GUID te verkrijgen voor voorlopig verwijderde (of inactieve) postvakken, voert u de volgende opdracht uit: `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`.  <br/> | `annb@contoso.onmicrosoft.com` <br/> Of  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Hiermee geeft u op of u het PST-bestand wilt importeren in het archiefpostvak van de gebruiker. Er zijn twee opties:  <br/><br/>**ONWAAR:** Het PST-bestand wordt geïmporteerd in het primaire postvak van de gebruiker.  <br/> **WAAR:** Het PST-bestand wordt geïmporteerd in het archiefpostvak van de gebruiker. Er wordt vanuit gegaan dat [het archiefpostvak van de gebruiker actief is](enable-archive-mailboxes.md). <br/><br/>Als u deze parameter instelt op `TRUE` en het archiefpostvak van de gebruiker is niet actief, dan mislukt de importbewerking voor die gebruiker. Als een importbewerking voor één gebruiker mislukt (omdat zijn of haar archiefpostvak niet actief is en deze eigenschap is ingesteld op `TRUE`), dan hebben de overige gebruikers hiervan geen last.  <br/>  Als u deze parameter leeg laat, wordt het PST-bestand geïmporteerd in het primaire postvak van de gebruiker.  <br/> <br/>**Opmerking:** Als u een PST-bestand wilt importeren in een archiefpostvak in de cloud van een gebruiker wiens primaire postvak zich on-premises bevindt, geeft u `TRUE` op voor deze parameter en geeft u het e-mailadres op van het on-premises gebruikerspostvak voor de `Mailbox`-parameter.  <br/> | `FALSE` <br/> Of  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Hiermee geeft u het postvak op waarin het PST-bestand wordt geïmporteerd.  <br/> <br/> Als u deze parameter leeg laat, wordt het PST-bestand geïmporteerd in een nieuwe map genaamd **Geïmporteerd** in de hoofdmap van het postvak (op hetzelfde niveau als de map Postvak IN en de andere standaardmappen).  <br/> <br/> Als u `/` opgeeft, worden de mappen en items in het PST-bestand geïmporteerd bovenaan de mapstructuur in het doelpostvak of archief. Als een map al bestaat in het doelpostvak (bijvoorbeeld standaardmappen zoals Postvak IN, Verzonden items en Verwijderde items), worden de items in die map in het PST-bestand samengevoegd in de bestaande map in het doelpostvak. Als het PST-bestand bijvoorbeeld een Postvak IN bevat, worden items in die map geïmporteerd in het Postvak IN in het doelpostvak. Nieuwe mappen worden gemaakt als ze nog niet bestaan in de mapstructuur voor het doelpostvak.  <br/><br/>  Als u `/<foldername>` opgeeft, worden de items  en mappen in het PST-bestand geïmporteerd in een map genaamd *\<foldername\>*. Als u bijvoorbeeld `/ImportedPst` gebruikt, worden de items geïmporteerd in een map genaamd **ImportedPst**. Deze map bevindt zich in het postvak van de gebruiker, op hetzelfde niveau als de map Postvak IN.  <br/><br/> **Tip:** Het is aan te raden te experimenteren met deze parameter in een aantal testbatches, zodat u kunt bepalen wat de beste locatie is voor het importeren van PST-bestanden.  <br/> |(laat leeg)  <br/> Of  <br/>  `/` <br/> Of  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Met deze optionele parameter geeft u een numerieke waarde op voor de codetabel die u wilt gebruiken voor het importeren van PST-bestanden in de ANSI-indeling. Deze parameter kunt u gebruiken voor het importeren van PST-bestanden van Chinese, Japanse of Koreaanse organisaties (CJK), omdat die talen gebruikmaken van DBCS-tekens voor tekencodering. Als u deze parameter niet gebruikt bij het importeren van PST-bestanden die DBCS-tekens gebruiken voor de namen van mappen in postvakken, zijn de namen van de mappen vaak vervormd na het importeren.  <br/><br/> Zie [Codetabel-id’s](/windows/win32/intl/code-page-identifiers) voor een lijst met ondersteunde waarden voor deze parameter.  <br/> <br/>**Opmerking:** Zoals eerder vermeld is dit een optionele parameter, die u niet hoeft te gebruiken in uw CSV-bestand. U kunt de parameter ook toevoegen en voor een of meer rijen leeg laten.  <br/> |(laat leeg)  <br/> Of  <br/>  `932` (de codetabel-id voor ANSI/OEM Japans)  <br/> |
    | `SPFileContainer` <br/> |Voor de PST-import laat u deze parameter leeg.  <br/> |Niet van toepassing  <br/> |
    | `SPManifestContainer` <br/> |Voor de PST-import laat u deze parameter leeg.  <br/> |Niet van toepassing  <br/> |
    | `SPSiteUrl` <br/> |Voor de PST-import laat u deze parameter leeg.  <br/> |Niet van toepassing  <br/> |

## <a name="step-5-create-a-pst-import-job"></a>Stap 5: maak een PST-importtaak

De volgende stap is het maken van een PST-importtaak in de importservice van Microsoft 365. Zoals hiervoor uitgelegd dient u hierbij het toewijzingsbestand voor de PST-import in dat u in stap 4 hebt gemaakt. Nadat u de nieuwe taak hebt gemaakt, analyseert Microsoft 365 de gegevens in de PST-bestanden en krijgt u de gelegenheid om te filteren welke gegevens daadwerkelijk worden geïmporteerd in de postvakken die u hebt opgegeven in het toewijzingsbestand voor de PST-import (zie [stap 6](#step-6-filter-data-and-start-the-pst-import-job)).
  
1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met de referenties van een beheerdersaccount in uw organisatie. 

2. In het linkerdeelvenster van het beveiligings- en compliancecentrum klikt u op **Informatiebeheer > Importeren > PST-bestanden importeren**.

3. Klik op de pagina **PST-bestanden importeren** op ![Pictogram toevoegen](../media/ITPro-EAC-AddIcon.gif) **Nieuwe importtaak**.

   > [!NOTE]
   > U moet de juiste machtigingen bezitten om de pagina **Importeren** te kunnen openen in het beveiligings- en compliancecentrum om een importtaak te kunnen maken. Zie het gedeelte **Voordat u begint** voor meer informatie. 

4. Typ een naam voor de PST-importtaak en klik op **Volgende**. U kunt kleine letters, getallen, streepjes en onderstrepingstekens gebruiken. U kunt geen hoofdletters of spaties in de naam gebruiken.

5. Op de pagina **Wilt u gegevens uploaden of verzenden?** klikt u op **Uw gegevens uploaden** en vervolgens op **Volgende**.

    ![Klikken op Uw gegevens uploaden om een importtaak voor het uploaden via het netwerk te maken](../media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. Klik in stap 4 op de pagina **Gegevens importeren** op de selectievakjes **Ik ben klaar met het uploaden van mijn bestanden** en **Ik heb een toewijzingsbestand**, en klik vervolgens op **Volgende**.

    ![Klik in stap 4 op de twee selectievakjes](../media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. Klik op de pagina **Het toewijzingsbestand selecteren** op **Toewijzingsbestand selecteren** om het CSV-toewijzingsbestand in te dienen dat u in stap 4 hebt gemaakt.

    ![Klik op Toewijzingsbestand selecteren om het CSV-bestand in te dienen dat u hebt gemaakt voor de importtaak](../media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. Wanneer de naam van het CSV-bestand wordt weergegeven onder **Naam toewijzingsbestand**, klikt u op **Valideren** om het CSV-bestand te controleren op fouten. 

    ![Klik op Valideren om het CSV-bestand te controleren op fouten.](../media/4680999d-5538-4059-b878-2736a5445037.png)
  
    Het CSV-bestand moet worden gevalideerd voordat u een PST-importtaak kunt maken. De bestandsnaam groen wordt als de validatie is voltooid. Als de validatie mislukt, klikt u op de koppeling **Logboek weergeven**. Er wordt een validatierapport geopend met een foutmelding voor elke rij in het bestand waarvoor de validatie is mislukt.

   > [!NOTE]
   > Zoals eerder aangegeven kan een toewijzingsbestand maximaal 500 rijen bevatten. De validatie mislukt als het toewijzingsbestand meer dan 500 rijen heeft. Om meer dan 500 PST-bestanden te importeren, moet u meerdere toewijzingsbestanden en meerdere importtaken maken.

9. Nadat het toewijzingsbestand is gevalideerd, leest u de voorwaarden en klikt u op het selectievakje.

10. Klik op **Opslaan** om de taak in te dienen en klik vervolgens op **Sluiten** als de taak is gemaakt.

    Er wordt een flyoutpagina weergegeven met de status **Analyse wordt uitgevoerd**, en de nieuwe importtaak wordt weergegeven in de lijst op de pagina **PST-bestanden importeren**.

11. Klik op **Vernieuwen** ![Pictogram vernieuwen](../media/O365-MDM-Policy-RefreshIcon.gif) om de statusinformatie bij te werken die wordt weergegeven in de kolom **Status**. Wanneer de analyse is voltooid en de gegevens klaar zijn om te worden geïmporteerd, wordt de status gewijzigd in **Analyse voltooid**.

    U kunt op de importtaak klikken om de flyoutpagina met de status weer te geven. Deze bevat meer gedetailleerde informatie over de importtaak, zoals de status van elk PST-bestand dat wordt vermeld in het toewijzingsbestand.

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Stap 6: filter gegevens en start de PST-importtaak

Nadat u de importtaak hebt gemaakt in stap 5, analyseert Microsoft 365 de gegevens in de PST-bestanden (op een veilige manier) door de leeftijd van de items en de verschillende berichttypen in de PST-bestanden te bepalen. Wanneer de analyse is voltooid en de gegevens klaar zijn om te worden geïmporteerd, hebt u de optie om de alle gegevens in de PST-bestanden te importeren of de hoeveelheid gegevens te beperken door filters te gebruiken om te bepalen welke gegevens er worden geïmporteerd.
  
1. Klik op de pagina **PST-bestanden importeren**, in het beveiligings- en compliancecentrum op **Klaar om te importeren in Office 365** voor de importtaak die u in stap 5 hebt gemaakt.

    ![Klik op Klaar om te importeren in Microsoft 365 naast de importtaak die u hebt gemaakt](../media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Er wordt een flyoutpagina weergegeven met informatie over de PST-bestanden en overige informatie over de importtaak.

2. Klik op de flyoutpagina op **Importeren in Office 365**.

    De pagina **Gegevens filteren** wordt weergegeven. Deze pagina bevat informatie uit de analyse van de PST-bestanden door Office 365, inclusief informatie over de leeftijd van de gegevens. U hebt nu de optie om te filteren welke gegevens worden geïmporteerd of alle gegevens te importeren. 

    ![U kunt de gegevens in het PST-bestand knippen of alles importeren](../media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. Voer een van de volgende handelingen uit:

   1. Als u hoeveelheid gegevens die u importeert wilt beperken, klikt u op **Ja, ik wil een filter gebruiken voor het importeren**.

      Zie [Gegevens filteren bij het importeren van PST-bestanden in Office 365](filter-data-when-importing-pst-files.md) voor gedetailleerde en stapsgewijze instructies voor het filteren van de gegevens in de PST-bestanden en het vervolgens starten van de importtaak.

      Of

   2. Als u alle gegevens in de PST-bestanden wilt importeren, klikt u op **Nee, ik wil alles importeren** en klikt u op **Volgende**.

4. Als u ervoor kiest alle gegevens te importeren, klikt u op **Gegevens importeren** om de importtaak te starten. 

   De status van de importtaak wordt weergegeven op de pagina **PST-bestanden importeren**. Klik op ![het pictogram](../media/O365-MDM-Policy-RefreshIcon.gif) **Vernieuwen** om de statusinformatie bij te werken die wordt weergegeven in de kolom **Status**. Klik op de importtaak om een flyoutpagina weer te geven met de status van elk PST-bestand dat wordt geïmporteerd. 

## <a name="more-information"></a>Meer informatie

- Waarom PST-bestanden importeren in Microsoft 365?

  - Het is een goede manier om de gearchiveerde berichtgegevens van uw organisatie te importeren in Microsoft 365.

  - De gegevens zijn beschikbaar voor gebruikers van alle soorten apparaten, omdat ze zijn opgeslagen in de cloud.

  - Er wordt zo voldaan aan nalevingsbehoeften van uw organisatie, omdat u Microsoft 365-compliancefuncties kunt toepassen op de gegevens van de PST-bestanden die u hebt geïmporteerd. Dit zijn:

  - Inschakelen van [archiefpostvakken](enable-archive-mailboxes.md) en [automatisch uitbreidende archieven](enable-unlimited-archiving.md) om gebruikers extra opslagruimte te geven om de gegevens op te slaan die u hebt geïmporteerd.

  - Postvakken instellen als [Juridische bewaring](./create-a-litigation-hold.md) om de gegevens te behouden die u hebt geïmporteerd.

  - [eDiscovery-hulpmiddelen](search-for-content.md) van Microsoft gebruiken om te zoeken naar de gegevens die u hebt geïmporteerd.

  - [Microsoft 365-retentiebeleid](retention.md) gebruiken om te bepalen hoelang de gegevens die u hebt geïmporteerd, worden behouden en welke actie er moet worden ondernomen nadat die periode is verstreken.

  - Zoeken naar het [auditlogboek](search-the-audit-log-in-security-and-compliance.md) voor postvakgerelateerde gebeurtenissen die van invloed zijn op de gegevens die u hebt geïmporteerd.

  - Gegevens importeren in [inactieve postvakken](create-and-manage-inactive-mailboxes.md) om gegevens te archiveren voor nalevingsdoeleinden. 

  - [Preventie van gegevensverlies](dlp-learn-about-dlp.md) gebruiken om te voorkomen dat vertrouwelijke gegevens buiten uw organisatie worden gelekt.
  
- Dit is een voorbeeld van de SAS-URL (Shared Access Signature) die u hebt verkregen in stap 1. Dit voorbeeld bevat ook de syntaxis voor de opdracht die u uitvoert in AzCopy.exe voor het uploaden van PST-bestanden. Neem maatregelen ter bescherming van de SAS-URL, net zoals voor het beschermen van wachtwoorden of andere beveiligingsinformatie.

    ```console
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    ```

- Zoals hiervoor uitgelegd schakelt de Office 365-importservice de instelling voor het blokkeren voor bewaren in (voor onbepaalde tijd) nadat de PST-bestanden zijn geïmporteerd in een postvak. Dit houdt in dat de eigenschap *RetentionHoldEnabled* wordt ingesteld op **Waar**, zodat het bewaarbeleid dat van toepassing is op het postvak niet wordt verwerkt. Dit geeft de eigenaar van het postvak de tijd om de net geïmporteerde berichten te beheren, doordat wordt voorkomen dat oudere berichten worden verwijderd of gearchiveerd op basis van een bewaarbeleid. Hier volgen enkele stappen voor het beheren van het blokkeren voor bewaren:

   - Na een bepaalde tijd kunt u het blokkeren voor bewaren uitschakelen door de opdracht **Set-Mailbox -RetentionHoldEnabled $false** uit te voeren. Zie [Een postvak blokkeren voor bewaren](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold) voor instructies.

   - U kunt het blokkeren configureren om het op een toekomstige datum uit te schakelen. U doet dit door de opdracht **Set-Mailbox -EndDateForRetentionHold *date*** uit te voeren. Bijvoorbeeld: het is vandaag 1 juni 2016 en u wilt de blokkering opheffen na 30 dagen. Daarvoor gebruikt u de volgende opdracht: **Set-Mailbox -EndDateForRetentionHold 7/1/2016**. In dit scenario laat u de eigenschap **RetentionHoldEnabled** ingesteld op *Waar*. Zie [Set-Mailbox](/powershell/module/exchange/set-mailbox) voor meer informatie.

   - U kunt de instellingen wijzigen van het bewaarbeleid dat van toepassing is op het postvak, zodat oudere items die worden geïmporteerd niet direct worden verwijderd of worden verplaatst naar het archiefpostvak van de gebruiker. U kunt bijvoorbeeld de bewaartermijn wijzigen van een beleid voor verwijderen of archiveren dat van toepassing is op het postvak. In dit scenario schakelt u het blokkeren voor bewaren uit voor het postvak nadat u het bewaarbeleid hebt gewijzigd. Zie [Een archief en een verwijderingsbeleid instellen voor postvakken in uw organisatie](set-up-an-archive-and-deletion-policy-for-mailboxes.md) voor meer informatie.

### <a name="how-the-import-process-works"></a>Zo werkt het IMAP-migratieproces
  
U kunt de optie gebruiken voor het uploaden via het netwerken en de importservice van Office 365 om PST-bestanden bulksgewijs te importeren in postvakken van gebruikers. Uploaden via het netwerk betekent dat u de PST-bestanden uploadt naar een tijdelijke opslagruimte in de Microsoft-cloud. De importservice van Office 365 kopieert de PST-bestanden vervolgens van de opslagruimte nar de postvakken van de gebruikers.
  
Hier ziet u een afbeelding en beschrijving van het uploadproces via het netwerk om PST-bestanden te importeren in postvakken in Office 365.
  
![Werkstroom van het netwerkuploadproces om PST-bestanden te importeren in Office 365](../media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **Het PST-importeerhulpmiddel en de sleutel voor de persoonlijke Azure-opslaglocatie downloaden:** de eerste stap is het downloaden van het opdrachtregelprogramma AzCopy en een toegangssleutel die wordt gebruikt om de PST-bestanden te uploaden naar een Azure-opslaglocatie in de Microsoft-cloud. U verkrijgt deze op de pagina **Importeren** in het beveiligings- en compliancecentrum. Met de sleutel (een zogenaamde SAS-sleutel (Secure Access Signature)) beschikt u over de benodigde machtigingen om de PST-bestanden te uploaden naar een persoonlijke en beveiligde Azure-opslaglocatie. Deze toegangssleutel is uniek voor uw organisatie en voorkomt onbevoegde toegang tot uw PST-bestanden nadat ze zijn geüpload naar de Microsoft-cloud. Voor het importeren van PST-bestanden hoeft uw organisatie geen apart Azure-abonnement te hebben. 

2. **De PST-bestanden uploaden naar de Azure-opslaglocatie:** de volgende stap is het hulpprogramma AzCopy.exe (gedownload in stap 1) te gebruiken om uw PST-bestanden te uploaden en op te slaan in een Azure-opslaglocatie die zich in hetzelfde regionale Microsoft-datacenter bevindt als uw organisatie. Als u de PST-bestanden die u wilt importeren, wilt uploaden, moeten ze zich bevinden in een bestandsshare of -server in uw organisatie.

    Er is een optionele stap die u kunt uitvoeren om de lijst met PST-bestanden te bekijken nadat ze zijn geüpload naar de Azure-opslaglocatie.

3. **Een PST-importtoewijzingsbestand maken**: nadat de PST-bestanden zijn geüpload naar de Azure-opslaglocatie is de volgende stap het maken van een bestand met door komma's gescheiden waarden (CSV) waarin wordt aangegeven in welke gebruikerspostvakken de PST-bestanden worden geïmporteerd. Een PST-bestand kan worden geïmporteerd in het primaire postvak of het archiefpostvak van een gebruiker. De Office 365-importservice gebruikt de gegevens in het CSV-bestand om de PST-bestanden te importeren.

4. **Een PST-importtaak maken**: de volgende stap is het maken van een PST-importtaak op de pagina **PST-bestanden importeren** in het beveiligings- en compliancecentrum en het PST-importtoewijzingsbestand te verzenden dat in de vorige stap is gemaakt. Nadat u de importtaak hebt gemaakt, analyseert Microsoft 365 de gegevens in de PST-bestanden en biedt u vervolgens de mogelijkheid om filters in te stellen die bepalen welke gegevens daadwerkelijk worden geïmporteerd in de postvakken die zijn opgegeven in het PST-importtoewijzingsbestand. 

5. **De PST-gegevens filteren die worden geïmporteerd in de postvakken**: nadat de importtaak is gemaakt en gestart, analyseert Microsoft 365 de gegevens in de PST-bestanden (veilig en beveiligd) door de leeftijd van de items en de verschillende berichttypen in de PST-bestanden te identificeren. Wanneer de analyse is voltooid en de gegevens klaar zijn om te worden geïmporteerd, hebt u de optie om de alle gegevens in de PST-bestanden te importeren of de hoeveelheid gegevens te beperken door filters te gebruiken om te bepalen welke gegevens er worden geïmporteerd.

6. **De PST-importtaak starten**: nadat de importtaak is gestart, gebruikt Microsoft 365 de informatie in het PST-importtoewijzingsbestand om de PST-bestanden vanuit de Azure-opslaglocatie te importeren in de postvakken van de gebruikers. Statusinformatie over de importtaak (inclusief informatie over elk PST-bestand dat wordt geïmporteerd) wordt weergegeven op de pagina **PST-bestanden importeren** in het beveiligings- en compliancecentrum. Wanneer de importtaak is voltooid, wordt de status voor de taak ingesteld op **Voltooid**.
