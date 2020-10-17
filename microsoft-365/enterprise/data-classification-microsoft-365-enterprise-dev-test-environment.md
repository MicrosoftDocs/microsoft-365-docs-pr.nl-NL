---
title: Gegevensclassificatie voor uw Microsoft 365-testomgeving voor ondernemingen
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
description: Gebruik deze test lab-handleiding voor het maken en gebruiken van labels voor bewaarbeleid voor documenten in uw Microsoft 365 voor Enterprise-test omgeving.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487730"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Gegevensclassificatie voor uw Microsoft 365-testomgeving voor ondernemingen

*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*

In dit artikel wordt uitgelegd hoe u gegevensclassificatie kunt configureren met labels voor bewaarbeleid in uw Microsoft 365 voor Enterprise-testomgeving.

Het classificeren van gegevens in de testomgeving omvat drie fasen:
- [Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Labels voor bewaarbeleid maken](#phase-2-create-retention-labels)
- [Fase 3: Labels voor bewaarbeleid toepassen op documenten](#phase-3-apply-retention-labels-to-documents)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u alleen Bewaar etiketten op een lichte manier wilt configureren met de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u de Bewaar labels van een gesimuleerde Enterprise-organisatie wilt configureren, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van labels voor bewaarbeleid is de gesimuleerde Enterprise-testomgeving niet vereist, waaronder een gesimuleerd intranet dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. Dit wordt hier als optie geboden, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt.

## <a name="phase-2-create-retention-labels"></a>Fase 2: Labels voor bewaarbeleid maken

In deze fase maakt u de etiketten voor bewaarbeleid voor de verschillende niveaus voorbehoud van mappen in SharePoint Online-documenten:

1. Meld u aan bij het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/homepage) met uw globale beheerdersaccount.
1. Selecteer op het tabblad **Start-Microsoft 365-beveiliging** van uw browser de optie **classificatie**  >  **Bewaar labels**.
1. Selecteer **een etiket maken**.
1. **Voer in** het deelvenster naam van **de naam uw** naam in de **naam van uw etiket**in en selecteer **volgende**.
1. Selecteer in het deelvenster met **descriptors voor bestandsplan** de optie **volgende**.
1. Stel in het deelvenster **etiketinstellingen** , indien nodig, **bewaren** in **op**aan en selecteer **volgende**.
1. Selecteer in het deelvenster **uw instellingen controleren** **de optie het etiket maken**.
1. Herhaal stappen 3-7 voor aanvullende labels met de volgende namen:
  - Privé
  - Gevoelig
  - Zeer vertrouwelijk
1. Selecteer in het deelvenster **Bewaar labels** de optie **etiketten publiceren**.
1. Selecteer in het deelvenster **Kies Labels voor publiceren** de optie **etiketten selecteren om te publiceren**.
1. Selecteer in het deelvenster **labels kiezen** de optie **toevoegen** en selecteer alle vier de etiketten.
1. Selecteer **toevoegen**en selecteer **gereed**.
1. Selecteer **volgende**in het deelvenster **Kies Labels die u wilt publiceren** .
1. Selecteer in het deelvenster **kieslocaties** de optie **volgende**.
1. Voer in het deelvenster **uw beleid een naam** geven in **voorbeeld van organisatie** in **naam**en selecteer **volgende**.
1. Selecteer in het deelvenster **uw instellingen controleren** de optie **etiketten publiceren**.
 
Het kan een paar minuten duren voordat de Bewaar etiketten zijn gepubliceerd.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: Labels voor bewaarbeleid toepassen op documenten

In deze fase ontdekt u het standaardgedrag van het Bewaar label voor bestanden in de map documenten van een SharePoint Online-site en wijzigt u het Bewaar label van een document handmatig.

Maak eerst een SharePoint Online-team site met gevoelige niveaus:
  
1. Meld u met een persoonlijk exemplaar van uw browser aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met uw globale beheerdersaccount.
1. Selecteer in de lijst met tegels de optie **SharePoint**.
1. Selecteer **site maken**op het tabblad nieuwe **SharePoint** in de browser.
1. Selecteer op de pagina **een site maken** de optie **team site**.
1. Voer in het vak **naam van team site** **SensitiveFiles**in.
1. Voer in het vak **Beschrijving van team site** de **SharePoint-site in voor gevoelige bestanden**.
1. Selecteer bij **privacyinstellingen**de optie **persoonlijke leden hebben toegang tot deze site**en selecteer **volgende**.
1. Selecteer in het deelvenster **wie wilt u toevoegen?** de optie **Voltooien**.
    
Vervolgens configureert u de map documenten van de team site van SensitiveFiles voor het gevoelige Bewaar label.
  
1. Selecteer op het tabblad **SensitiveFiles** van uw browser de optie **documenten**.
1. Selecteer het pictogram **instellingen** en selecteer vervolgens **Bibliotheekinstellingen**.
1. Selecteer onder **machtigingen en beheer**de optie **label toepassen op items in deze lijst of bibliotheek**. Als deze optie niet wordt weergegeven, zijn uw Bewaar etiketten nog niet gepubliceerd. Probeer deze stap later nog eens.
1. Selecteer in de vervolgkeuzelijst **instellingen-labels toepassen**de optie **gevoelig** en selecteer vervolgens **Opslaan**.

Vervolgens maakt u een nieuw document op de site van SensitiveFiles en wijzigt u het Bewaar label.
    
1. Selecteer in de map documenten de optie **Nieuw**  >  **Word-document**.
1. Typ wat tekst in het lege document. Wacht totdat de tekst is opgeslagen.
1. Selecteer in de menubalk **gedeelde documenten**.
1. Selecteer naast de bestandsnaam van de **Document.docx** de drie puntjes en selecteer vervolgens **Details**.
1. Selecteer in het rechterdeelvenster, in de sectie **Eigenschappen** , onder **Bewaar label toepassen**, het document met het **gevoelige** Bewaar label automatisch toegepast.
1. Klik op **Alles bewerken**.
1. Selecteer in het deelvenster **Document.docx** , onder **Bewaar etiket toepassen**, de optie voor **zeer vertrouwelijke** etiketten en selecteer vervolgens **Opslaan**.

## <a name="next-step"></a>Volgende stap

Verken de functies en mogelijkheden van extra [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
