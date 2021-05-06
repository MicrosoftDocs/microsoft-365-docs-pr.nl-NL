---
title: Detectie van advocaten-clientrechten instellen in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Gebruik het detectiemodel voor advocaten-clientprivilege om op machine learning gebaseerde detectie van bevoorrechte inhoud te gebruiken bij het bekijken van inhoud in een Advanced eDiscovery geval.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/03/2020
ms.locfileid: "52161491"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a>Detectie van advocaten-clientrechten instellen in Advanced eDiscovery

Een belangrijk en duur aspect van de revisiefase van een eDiscovery-proces is het controleren van documenten op bevoorrechte inhoud. Advanced eDiscovery biedt machine learning-gebaseerde detectie van bevoorrechte inhoud om dit proces efficiënter te maken. Deze functie wordt de *detectie van advocaten-clientvoorrechten genoemd.*

## <a name="how-does-it-work"></a>Hoe werkt dit?

Wanneer de detectie van advocaten-clientrechten is ingeschakeld, worden alle documenten in een revisieset verwerkt door het detectiemodel voor advocaten-clientrechten wanneer u de gegevens [in](analyzing-data-in-review-set.md) de revisieset analyseert. Het model zoekt naar twee dingen:

- Bevoorrechte inhoud: het model maakt gebruik van machine learning om de kans te bepalen dat het document inhoud bevat die juridisch van aard is.

- Deelnemers: als onderdeel van het instellen van de detectie van advocaten-clientrechten, moet u een lijst met advocaten voor uw organisatie indienen. Het model vergelijkt vervolgens de deelnemers aan het document met de lijst met advocaten om te bepalen of een document ten minste één deelnemer aan de advocatenlijst heeft.

Het model produceert de volgende drie eigenschappen voor elk document:

- **AttorneyClientPrivilegeScore:** De kans dat het document juridisch van aard is; de waarden voor de score liggen tussen **0** en **1**.

- **HasAttorney:** Deze eigenschap is ingesteld op **waar** als een van de deelnemers aan het document wordt vermeld in de lijst met advocaten. anders is de waarde **onwaar.** De waarde is ook ingesteld op **onwaar** als uw organisatie geen advocatenlijst heeft geüpload.

- **IsPrivilege:** Deze eigenschap is ingesteld op **waar** als de waarde voor **AttorneyClientPrivilegeScore** boven de drempel ligt of als het document een deelnemer aan de advocatenlijst heeft.  anders is de waarde ingesteld op **onwaar**.

Deze eigenschappen (en de bijbehorende waarden) worden toegevoegd aan de bestandsmetagegevens van de documenten in een revisieset, zoals wordt weergegeven in de volgende schermafbeelding:

![Eigenschappen van advocaten-clientrechten die worden weergegeven in bestandsmetagegevens](../media/AeDAttorneyClientPrivilegeMetadata.png)

Deze drie eigenschappen kunnen ook worden doorzocht in een revisieset. Zie Query's [uitvoeren op de gegevens in een revisieset voor meer informatie.](review-set-search.md)

## <a name="set-up-the-attorney-client-privilege-detection-model"></a>Het detectiemodel voor advocaten-clientrechten instellen

Als u het detectiemodel voor advocaten-clientrechten wilt inschakelen, moet uw organisatie het inschakelen en vervolgens een lijst met advocaten uploaden.

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a>Stap 1: Detectie van advocaten-clientrechten in- en uit-

Een persoon die een eDiscovery-beheerder in uw organisatie is (lid van de subgroep eDiscovery-beheerder in de rollengroep eDiscovery Manager) moet het model beschikbaar stellen in uw Advanced eDiscovery gevallen.

1. Ga in het & Compliancecentrum naar **eDiscovery > Advanced eDiscovery.**

2. Klik op **Advanced eDiscovery** startpagina in  de Instellingen op Globale analyse-instellingen **configureren.**

   ![Selecteer 'Experimentele functies configureren'](../media/AeDExperimentalFeatures.png)

3. Selecteer op **het tabblad Analyse-instellingen** **de instelling Advocaten-clientvoorrecht beheren.**

4. Gebruik op **de flyout pagina Attorney-client privilege** de schakelknop om de functie in te schakelen en selecteer **opslaan.**

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>Stap 2: Upload een lijst met advocaten (optioneel)

Als u optimaal wilt profiteren van het detectiemodel voor advocaten-clientprivilege en gebruik wilt maken van de resultaten van de eerder beschreven detectie has **attorney** of **Potentially Privileged,** raden we u aan een lijst met e-mailadressen te uploaden voor de advocaten en juridisch personeel die voor uw organisatie werken. 

Een lijst met advocaten uploaden voor gebruik door het detectiemodel voor advocaten-clientrechten:

1. Maak een .csv bestand (zonder veldnamenrij) en voeg het e-mailadres voor elke juiste persoon toe aan een aparte regel. Sla dit bestand op uw lokale computer op.

2. Selecteer op **Advanced eDiscovery** startpagina in  de tegel Instellingen experimentele functies configureren **en** selecteer vervolgens De instelling **Advocaten-client privilege beheren.**

   De **pagina Advocaten-clientvoorrecht** wordt weergegeven en de schakelaar Detectie van **advocaten-clientrechten** is ingeschakeld.

   ![Flyoutpagina advocaten-client privilege](../media/AeDUploadAttorneyList.png)

3. Selecteer **Bladeren** en selecteer vervolgens het .csv bestand dat u in stap 1 hebt gemaakt.

4. Selecteer **Opslaan om** de lijst met advocaten te uploaden.

## <a name="use-the-attorney-client-privilege-detection-model"></a>Het detectiemodel voor advocaten-clientrechten gebruiken

Volg de stappen in deze sectie om de detectie van advocaten-clientrechten te gebruiken voor documenten in een revisieset.

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>Stap 1: Een smart tag-groep maken met het detectiemodel voor advocaten-clientrechten

Een van de belangrijkste manieren om de resultaten van de detectie van advocaten-clientrechten in uw beoordelingsproces te zien, is door een smart tag-groep te gebruiken. Een groep met slimme tags geeft de resultaten aan van de detectie van het privilege van de advocatenclient en toont de resultaten in de regel naast de tags in een groep met slimme labels. Op deze manier kunt u snel potentieel bevoorrechte documenten identificeren tijdens de documentbeoordeling. Daarnaast kunt u de tags in de groep slimme labels ook gebruiken om documenten te taggen als bevoorrecht of niet-bevoorrecht. Zie Slimme tags instellen in Advanced eDiscovery voor meer informatie over slimme [tags.](smart-tags.md)

1. Selecteer in de revisieset met de documenten die u  hebt geanalyseerd in stap 1 de optie Controleset beheren en selecteer **vervolgens Tags beheren.**
 
2. Selecteer **onder Tags** de pull-down naast De groep **Toevoegen** en selecteer vervolgens Groep Slimme **tags toevoegen.**

   ![Selecteer 'Groep slimme tags toevoegen'](../media/AeDCreateSmartTag.png)

3. Kies op **de pagina Kies een model voor uw slimme tag** de optie **Selecteren** naast **Attorney-client privilege.**

   Er wordt een taggroep met de naam **Attorney-client privilege** weergegeven. Het bevat twee onderliggende tags **met** de naam Positief **en** Negatief, die overeenkomen met de mogelijke resultaten die door het model worden geproduceerd.

   ![Smart taggroep Advocaten-client privilege](../media/AeDAttorneyClientSmartTagGroup.png)

3. Wijzig de naam van de taggroep en de tags die geschikt zijn voor uw beoordeling. U kunt bijvoorbeeld de naam Positief **wijzigen in** **Bevoorrecht** en **Negatief in** **Niet geprivilegieerd.**

### <a name="step-2-analyze-a-review-set"></a>Stap 2: Een revisieset analyseren

Wanneer u de documenten in een revisieset analyseert, wordt het detectiemodel voor advocaten-clientrechten ook uitgevoerd en worden de bijbehorende eigenschappen (beschreven in Hoe werkt [het?](#how-does-it-work) toegevoegd aan elk document in de revisieset). Zie Gegevens analyseren in een revisieset in Advanced eDiscovery voor meer informatie over het analyseren van gegevens [in de revisieset.](analyzing-data-in-review-set.md)

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a>Stap 3: De groep slimme tags gebruiken voor het bekijken van bevoorrechte inhoud

Na het analyseren van de revisieset en het instellen van slimme tags, is de volgende stap het controleren van de documenten. Als het model heeft vastgesteld dat het document potentieel  geprivilegieerd is, geeft de bijbehorende slimme tag in het deelvenster Labelen de volgende resultaten aan die zijn geproduceerd door de detectie van het advocaten-clientprivilege:

- Als het document inhoud bevat die juridisch van aard kan zijn, wordt het label **Juridische** inhoud weergegeven naast de bijbehorende slimme tag (in dit geval de **standaard-positieve** tag).

- Als het document een deelnemer bevat die is gevonden in de advocatenlijst van uw organisatie, wordt het label **Attorney** weergegeven naast de bijbehorende slimme tag (in dit geval ook de **standaard-positieve** tag).

- Als het document inhoud bevat die juridisch van aard kan zijn en  een  deelnemer heeft gevonden in de advocatenlijst, worden zowel de labels Juridische inhoud als Advocaten weergegeven.  

Als in het model wordt bepaald dat een document geen inhoud bevat die juridisch van aard is of die geen deelnemer uit de lijst met advocaten bevat, wordt geen van beide etiketten weergegeven in het labelvenster.

De volgende schermafbeeldingen bevatten bijvoorbeeld twee documenten. De eerste bevat inhoud die juridisch van aard is en die een deelnemer heeft gevonden in de lijst met advocaten. De tweede bevat geen van beide en geeft daarom geen etiketten weer.

![Document met inhoudslabels voor advocaten en juridische inhoud](../media/AeDTaggingPanelLegalContentAttorney.png)

![Document zonder etiketten](../media/AeDTaggingPanelNegative.png)

Nadat u een document hebt beoordeeld om te zien of het bevoorrechte inhoud bevat, kunt u het document taggen met de juiste tag.
