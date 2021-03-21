---
title: Gegevensclassificatie voor uw Microsoft 365 voor ondernemingstestomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Gebruik deze testlaboratoriumhandleiding om bewaarlabels voor documenten te maken en te gebruiken in uw Microsoft 365 voor ondernemingstestomgeving.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919186"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Gegevensclassificatie voor uw Microsoft 365 voor ondernemingstestomgeving

*Deze testlaborator kan worden gebruikt voor testomgevingen van Microsoft 365 voor bedrijven en Office 365 Enterprise.*

In dit artikel wordt beschreven hoe u gegevensclassificatie configureert met bewaarlabels in uw Microsoft 365 voor ondernemingstestomgeving.

Het classificeren van gegevens in uw testomgeving bestaat uit drie fasen:
- [Fase 1: Uw Microsoft 365 voor ondernemingstestomgeving opbouwen](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Bewaarlabels maken](#phase-2-create-retention-labels)
- [Fase 3: Bewaarlabels toepassen op documenten](#phase-3-apply-retention-labels-to-documents)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Ga naar [Microsoft 365 for enterprise Test Lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)Stack voor een visuele kaart voor alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide Stack.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 voor ondernemingstestomgeving opbouwen

Als u alleen de bewaarlabels op een lichtgewicht manier wilt configureren met de minimumvereisten, volgt u de instructies in [de lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u bewaarlabels wilt configureren in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van bewaarlabels is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als een optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.

## <a name="phase-2-create-retention-labels"></a>Fase 2: Bewaarlabels maken

Maak in deze fase de bewaarlabels voor de verschillende bewaarniveaus voor SharePoint Online-documentenmappen:

1. Meld u aan bij [het Microsoft 365-beveiligingscentrum](https://security.microsoft.com/homepage) met uw globale beheerdersaccount.
1. Selecteer classificatiebewaringslabels op het **tabblad Start - Microsoft 365-beveiliging** van   >  **uw** browser.
1. Selecteer **Een label maken.**
1. Voer in **het deelvenster** Naam uw label interne **openbare** naam in naam van uw **label** in en selecteer **volgende**.
1. Selecteer volgende in het deelvenster  **Bestandsplandescriptors.**
1. Stel in **het deelvenster** Labelinstellingen indien nodig **bewaaring** in op **Aan** en selecteer **vervolgens Volgende**.
1. Selecteer in **het deelvenster Uw instellingen** controleren de optie Het label **maken.**
1. Herhaal stap 3-7 voor extra labels met deze namen:
  - Privé
  - Gevoelig
  - Zeer vertrouwelijk
1. Selecteer in **het deelvenster Bewaarlabels** de optie **Labels publiceren.**
1. Selecteer labels **kiezen om te** publiceren in het deelvenster Labels kiezen om te **publiceren.**
1. Selecteer in **het deelvenster Labels** kiezen de optie **Toevoegen** en selecteer alle vier labels.
1. Selecteer **Toevoegen** en selecteer vervolgens **Klaar.**
1. Selecteer volgende **in het deelvenster Labels kiezen** om te **publiceren.**
1. Selecteer volgende **in het** deelvenster Locaties **kiezen.**
1. Voer in **het deelvenster Naam uw beleid** de optie **Voorbeeldorganisatie** in **Naam** in en selecteer **volgende**.
1. Selecteer in **het deelvenster** Uw instellingen controleren de optie **Labels publiceren.**
 
Het kan enkele minuten duren voordat de bewaarlabels zijn gepubliceerd.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: Bewaarlabels toepassen op documenten

In deze fase ontdekt u het standaardgedrag van bewaarlabels voor bestanden in de map Documenten van een SharePoint Online-site en wijzigt u handmatig het bewaarlabel van een document.

Maak eerst een SharePoint Online-teamsite op gevoelig niveau:
  
1. Meld u met een privé-exemplaar van uw browser aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met uw globale beheerdersaccount.
1. Selecteer SharePoint in de lijst met **tegels.**
1. Selecteer site maken op het **nieuwe tabblad SharePoint** in **uw browser.**
1. Selecteer teamsite **op de pagina** Een **site maken.**
1. Voer in **het vak Teamsitenaam** **SensitiveFiles in.**
1. Voer in **het vak Teamsitebeschrijving** **SharePoint-site voor gevoelige bestanden in.**
1. Selecteer **in Privacy-instellingen** de optie **Privé- alleen leden** hebben toegang tot deze site en selecteren vervolgens **Volgende.**
1. Selecteer voltooien in het deelvenster Wie wilt **u toevoegen?** **.**
    
Configureer vervolgens de map Documenten van de teamsite SensitiveFiles voor het label Gevoelige bewaring.
  
1. Selecteer documenten **op het tabblad SensitiveFiles** van **uw** browser.
1. Selecteer het **pictogram** Instellingen en selecteer vervolgens **Bibliotheekinstellingen.**
1. Selecteer **onder Machtigingen en beheer** de optie Label toepassen op items in deze lijst of **bibliotheek.** Als deze optie niet wordt weergegeven, zijn uw bewaarlabels nog niet gepubliceerd. Probeer deze stap op een later tijdstip.
1. Selecteer **in Instellingen-label** toepassen de optie **Gevoelig** in de vervolgkeuzekeuzemenu en selecteer **vervolgens Opslaan.**

Maak vervolgens een nieuw document op de site SensitiveFiles en wijzig het bewaarlabel.
    
1. Selecteer nieuw   >  **Word-document** in de map documenten.
1. Voer tekst in het lege document in. Wacht totdat de tekst is opgeslagen.
1. Selecteer gedeelde documenten op de **menubalk.**
1. Selecteer naast **Document.docx** bestandsnaam het verticale beletselteken en selecteer **vervolgens Details**.
1. In het rechterdeelvenster, in de sectie Eigenschappen, onder **Bewaarlabel** toepassen, wordt het label Gevoelige bewaring automatisch toegepast op het document.  
1. Klik **op Alles bewerken.**
1. Selecteer in **Document.docx** deelvenster Onder **Bewaarlabel toepassen** het label Zeer **vertrouwelijk** en selecteer **opslaan.**

## <a name="next-step"></a>Volgende stap

Ontdek extra [functies en](m365-enterprise-test-lab-guides.md#information-protection) mogelijkheden voor informatiebeveiliging in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)