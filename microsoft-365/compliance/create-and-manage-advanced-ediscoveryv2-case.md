---
title: Maak en beheer Advanced eDiscovery zaken in Microsoft 365
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
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In dit artikel wordt beschreven hoe u een aantal Advanced eDiscovery kunt maken en beheren. De eerste stap is het maken van een case en het gebruik van Advanced eDiscovery functies en functionaliteit.
ms.openlocfilehash: 95e88bb071476de1ed66b3ffaa8942f0a9df89c2
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311638"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Een Advanced eDiscovery maken en beheren

Na het instellen Advanced eDiscovery en het toewijzen van machtigingen aan [eDiscovery-managers](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) in uw organisatie die zaken beheren, is de volgende stap het maken en beheren van een zaak.

Dit artikel bevat ook een overzicht op hoog niveau van het gebruik van zaken om de werkstroom Advanced eDiscovery voor een juridische zaak of andere soorten onderzoeken te beheren.

## <a name="create-a-case"></a>Een zaak maken

Volg de volgende stappen om een zaak te maken en leden toe te voegen. De gebruiker die de zaak maakt, wordt automatisch toegevoegd als lid. Leden van de zaak hebben toegang tot de zaak in het Microsoft 365 compliancecentrum en kunnen Advanced eDiscovery uitvoeren.

1. Ga naar en meld u aan met de referenties voor gebruikersaccounts die zijn toegewezen <https://compliance.microsoft.com> aan eDiscovery-machtigingen. Leden van de rollengroep Organisatiebeheer kunnen ook Advanced eDiscovery maken.

2. Klik in het linkernavigatiedeelvenster van het Microsoft 365 compliancecentrum op **Alles weergeven** en klik vervolgens op **eDiscovery > Geavanceerd.**

3. Klik op **Advanced eDiscovery** pagina op het **tabblad Gevallen** en klik vervolgens op Een **zaak maken.**

4. Geef op de pagina Nieuw **eDiscovery-hoofddeksel** een naam (vereist) op en typ vervolgens een optioneel hoofddekselnummer en een beschrijving. De naam van de zaak moet uniek zijn in uw organisatie.

5. Klik **op Opslaan** om de zaak te maken.

   De nieuwe zaak wordt gemaakt en **het Instellingen** in de nieuwe zaak wordt weergegeven.

6. Klik op **de & access-machtigingen** op het **Instellingen** op **Selecteren.**

7. Klik op **de pagina Manage this case** flyout onder Leden **beheren** op **Toevoegen** om leden aan de zaak toe te voegen.

8. Schakel in de lijst met personen het selectievakje in naast de namen van de personen die u aan de zaak wilt toevoegen. Zoals eerder uitgelegd, moet u ervoor zorgen dat de personen die u aan de zaak toevoegt, de juiste eDiscovery-machtigingen hebben gekregen.

9. Nadat u de personen hebt geselecteerd die u wilt toevoegen als leden van de zaak, klikt u op **Toevoegen.**

10. Klik op **de pagina Dit geval** beheren op Opslaan **om** de nieuwe lijst met hoofdcaseleden op te slaan.

11. Klik op **het tabblad** Start om naar de startpagina van de zaak te gaan.

## <a name="manage-the-workflow"></a>De werkstroom beheren

Als u aan de slag wilt met Advanced eDiscovery, is hier een basiswerkstroom die is afgestemd op veelgebruikte [eDiscovery-procedures.](advanced-ediscovery-edrm.md) In elk van deze stappen markeren we ook een aantal uitgebreide Advanced eDiscovery functionaliteit die u kunt verkennen.

![Advanced eDiscovery werkstroom](../media/AeDWorkflow.png)

1. **[Voeg bewaarders en](add-custodians-to-case.md) [niet-bewaardergegevensbronnen toe](non-custodial-data-sources.md) aan de zaak.** De eerste stap na het maken van een zaak is het toevoegen van beheerders. Een *bewaarder* is een persoon die beheersbeheer heeft over een document of elektronisch bestand dat relevant kan zijn voor de zaak. Daarnaast kunt u gegevensbronnen toevoegen die niet zijn gekoppeld aan een specifieke gebruiker, maar die mogelijk relevant zijn voor de zaak.

   Hier vindt u enkele dingen die gebeuren (of dat u kunt doen) wanneer u beheerders toevoegt aan een zaak:

   - Gegevens in het Exchange-postvak van de bewaarder, OneDrive-account en alle Microsoft Teams- of Yammer-groepen waar de bewaarder lid van is, kunnen worden 'gemarkeerd' als bewaargegevens in het geval.
  
   - Bewaardergegevens worden opnieuw geïndexeerd (door een proces genaamd *Geavanceerd indexeren).* Hiermee kunt u het zoeken naar de zoekactie optimaliseren in de volgende stap.
  
   - U kunt bewaargegevens in de wacht zetten. Hierdoor blijven gegevens behouden die mogelijk relevant zijn voor de zaak tijdens het onderzoek.
  
   - U kunt andere gegevensbronnen koppelen aan een bewaarder (u kunt bijvoorbeeld een SharePoint-site of Microsoft 365-groep koppelen aan een bewaarder), zodat deze gegevens opnieuw kunnen worden geïndexeerd, in de wacht worden geplaatst en kunnen worden doorzocht, net zoals de gegevens in het postvak of OneDrive-account van de bewaarder.

   - U kunt de [communicatiewerkstroom](managing-custodian-communications.md) in Advanced eDiscovery gebruiken om een melding over een wettelijke bewaarstatus naar beheerders te verzenden.

2. **[Relevante inhoud verzamelen uit gegevensbronnen.](create-draft-collection.md)** Nadat u beheerders en niet-bewaardergegevensbronnen aan een zaak hebt toevoegen, gebruikt u het ingebouwde hulpprogramma voor verzamelingen om in deze gegevensbronnen te zoeken naar inhoud die relevant kan zijn voor de zaak. U gebruikt trefwoorden, eigenschappen en [](building-search-queries.md) voorwaarden om zoekquery's te maken die zoekresultaten retourneren met de gegevens die waarschijnlijk relevant zijn voor de zaak. U kunt ook:

   - Bekijk [verzamelingsstatistieken](collection-statistics-reports.md) die u kunnen helpen een verzameling te verfijnen om de resultaten te verfijnen.

   - Bekijk een voorbeeld van de verzameling om snel te controleren of de relevante gegevens worden gevonden.

   - Een query wijzigen en de verzameling opnieuw uitvoeren.

3. **[Verzameling aan een revisieset verbinden.](commit-draft-collection.md)** Nadat u hebt geconfigureerd en geverifieerd dat een zoekopdracht de gewenste gegevens retourneert, is de volgende stap het toevoegen van de zoekresultaten aan een revisieset. Wanneer u gegevens toevoegt aan een revisieset, worden items van de oorspronkelijke locatie gekopieerd naar een veilige Azure Storage locatie. De gegevens worden opnieuw geïndexeerd om deze te optimaliseren voor grondige en snelle zoekopdrachten bij het controleren en analyseren van items in de revisieset. Daarnaast kunt u ook [niet-Office 365 toevoegen aan een revisieset.](load-non-office-365-data-into-a-review-set.md)

   Er is ook een speciaal soort revisieset waar u gegevens aan kunt toevoegen, een *zogenaamde gespreksbeoordelingsset.* Deze typen beoordelingensets bieden mogelijkheden voor het herstellen van gesprekken om gesprekken met discussielijn te reconstrueren, te bekijken en te exporteren, zoals gesprekken in Microsoft Teams. Zie Gesprekken bekijken [in Advanced eDiscovery.](conversation-review-sets.md)

4. **Bekijk en analyseer gegevens in een revisieset.** Nu gegevens zich in een revisieset hebben, kunt u een groot aantal hulpprogramma's en mogelijkheden gebruiken om de casegegevens weer te geven en te analyseren, met als doel de gegevensset te beperken tot wat het meest relevant is voor de zaak die u onderzoekt. Hier ziet u een lijst met enkele hulpprogramma's en mogelijkheden die u tijdens dit proces kunt gebruiken.

   - [Documenten weergeven.](view-documents-in-review-set.md) Dit omvat het weergeven van de metagegevens voor elk document in een revisieset en het weergeven van het document in de oorspronkelijke versie of tekstversie.

   - [Query's en filters maken.](review-set-search.md) U maakt zoekquery's met behulp van [](document-metadata-fields-in-advanced-ediscovery.md)verschillende zoekcriteria (waaronder de mogelijkheid om alle eigenschappen van bestandsmetagegevens te doorzoeken) om de casegegevens verder te verfijnen en te verwijderen tot wat het meest relevant is voor de zaak. U kunt ook filters voor revisiesets gebruiken om snel andere voorwaarden toe te passen op de resultaten van een zoekquery om deze resultaten verder te verfijnen. 

   - [Tags maken en gebruiken.](tagging-documents.md) U kunt tags toepassen op documenten in een revisieset om te bepalen welke reageren (of niet reageren op de zaak) en deze tags vervolgens gebruiken bij het maken van zoekquery's om de gemarkeerde documenten op te nemen of uit te sluiten. U kunt ook labelen om te bepalen welke documenten u wilt exporteren.

   - [Aantekeningen maken en documenten redacteren](view-documents-in-review-set.md#annotate-view). U kunt het hulpmiddel aantekeningen gebruiken in een revisie om aantekeningen te maken bij documenten en inhoud in documenten te redacteren als werkproduct. We genereren tijdens de controle een PDF-versie van een geannoteerd of opnieuw gemaakt document om het risico op het exporteren van de niet-uitgevoerde oorspronkelijke versie van het document te beperken.

   - [Casegegevens analyseren.](analyzing-data-in-review-set.md) De analysefunctionaliteit in Advanced eDiscovery is krachtig. Nadat u analyses hebt uitgevoerd op de gegevens in de revisieset, voeren we analyses uit, zoals bijna dubbele detectie, e-mailthreading en thema's, waardoor het aantal documenten dat u moet controleren, kan worden beperkt. We genereren ook analyserapporten die het resultaat van het uitvoeren van analyses samenvatten. Zoals eerder is uitgelegd, wordt bij het uitvoeren van analyses ook het detectiemodel voor [bevoegdheden voor advocatenclient uitgevoerd.](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)

5. **Casegegevens exporteren en downloaden.** Een laatste stap na het verzamelen, controleren en analyseren van casegegevens is het exporteren van deze gegevens uit Advanced eDiscovery voor externe controle of ter controle door personen buiten het onderzoeksteam. Het exporteren van gegevens is een proces in twee stappen. De eerste stap is om [gegevens](export-documents-from-review-set.md) uit de revisieset te exporteren en deze te kopiëren naar een andere Azure Storage locatie (een locatie die wordt geleverd door Microsoft of een die door uw organisatie wordt beheerd). Vervolgens gebruikt u Azure Storage Explorer om [de gegevens](download-export-jobs.md) naar een lokale computer te downloaden. Naast de geëxporteerde gegevensbestanden bevat het exportpakket ook een exportrapport, een overzichtsrapport en een foutrapport.

## <a name="advanced-ediscovery-architecture"></a>Advanced eDiscovery architectuur

Hier ziet u een architectuurdiagram met de Advanced eDiscovery-endwerkstroom in een enkele geoomgeving en in een multi-geoomgeving en de end-to-end-gegevensstroom die is uitgelijnd met het referentiemodel voor elektronische [detectie.](overview-ediscovery-20.md#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)

[![Modelposter: Advanced eDiscovery Architectuur in Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Weergeven als een afbeelding](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Downloaden als PDF-bestand](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Downloaden als een Visio bestand](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
