---
title: Gegevensclassificatie voor uw Microsoft 365 Enterprise-testomgeving
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
description: Gebruik deze Test Lab-handleiding voor het maken en gebruiken van Office 365-bewaarlabels in documenten in uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: 6534eff67e9c91423eb6f81415cb3ef2e965dcc1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812028"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Gegevensclassificatie voor uw Microsoft 365 Enterprise-testomgeving

*Deze Test Lab Guide kan worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*

Met de instructies in dit artikel configureert u gegevensclassificatie met office 365-bewaarlabels in uw Microsoft 365 Enterprise-testomgeving.

![Lab-handleidingen testen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u alleen office 365-bewaarlabels op een lichtgewicht manier wilt configureren met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u Office 365-bewaarlabels in een gesimuleerde onderneming wilt configureren, volgt u de instructies in [pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van Office 365-bewaarlabels is de gesimuleerde bedrijfstestomgeving niet vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als optie verstrekt, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 

## <a name="phase-2-create-office-365-retention-labels"></a>Fase 2: Bewaarlabels voor Office 365 maken

In deze fase maakt u de bewaarlabels voor de verschillende retentieniveaus voor SharePoint Online-documentenmappen.

1. Meld u aan bij het [Microsoft 365-beveiligingscentrum](https://security.microsoft.com/homepage) met uw wereldwijde beheerdersaccount.
    
2. Klik op het **tabblad Start - Microsoft 365** van uw browser op Labels classificatie > **behouden**.
    
3. Klik **op Een label maken**.
    
4. Typ In het deelvenster **Naam van uw label** de tekst Intern **openbaar** in Naam van **uw label**en klik op **Volgende**.

5. Klik in het deelvenster **Beschrijvingen van bestandsplannen** op **Volgende**.
    
6. Stel in het deelvenster **Labelinstellingen** indien nodig **Retentie** in **op Aan**en klik op **Volgende**.
    
7. Klik **in** het deelvenster Instellingen controleren op **Het label maken**.
    
8. Herhaal stap 3-7 voor extra labels met deze namen:
    
  - Privé
    
  - Gevoelige
    
  - Zeer vertrouwelijk
  
9. Klik in het deelvenster **Bewaarlabels** op **Labels publiceren**.
    
10. Klik **in** het deelvenster Labels kiezen om te publiceren op Labels kiezen om te **publiceren**.
    
11. Klik **in** het deelvenster Labels kiezen op **Toevoegen** en selecteer alle vier de labels.
    
12. Klik **op Toevoegen**en klik vervolgens op **Gereed.**
    
13. Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.
    
14. Klik in het deelvenster **Locaties kiezen** op **Volgende**.
    
15. Typ **Voorbeeldorganisatie** in **Naam**in het **deelvenster Naam en** klik op **Volgende**.
    
16. Klik in het deelvenster **Instellingen controleren** op **Labels publiceren**.
 
Houd er rekening mee dat het enkele minuten kan duren voordat de bewaarlabels zijn gepubliceerd.

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>Fase 3: Bewaarlabels van Office 365 toepassen op documenten

In deze fase ontdekt u het standaardlabelgedrag voor bestanden in de map Documenten van een SharePoint Online-site en wijzigt u handmatig het bewaarlabel van een document.

Maak eerst een SharePoint Online-teamsite op gevoelig niveau:
  
1. Meld u met een privé-exemplaar van uw browser aan bij de [Office 365-portal](https://portal.office.com) met uw globale beheerdersaccount.
    
2. Klik in de lijst met tegels op **SharePoint**.
    
3. Klik op het nieuwe **tabblad SharePoint** in uw browser op **Site maken**.
    
4. Klik **op de pagina Een site maken** op **Teamsite**.
    
5. Typ **Gevoelige bestanden**in **teamsitenaam**.
    
6. Typ **SharePoint-site voor gevoelige bestanden**in **teamsitebeschrijving**.
    
7.  Selecteer **privé-instellingen**en selecteer **deze site**en klik vervolgens op **Volgende**.
    
8. Klik in het deelvenster Wie wilt **Finish** **u toevoegen?**
    
Configureer vervolgens de map Documenten van de teamsite SensitiveFiles voor het label Gevoelige bewaaropslag.
  
1. Klik op het tabblad **SensitiveFiles** van uw browser op **Documenten**.
    
2. Klik op het pictogram Instellingen en klik vervolgens op **Bibliotheekinstellingen**.
    
3. Klik **onder Machtigingen en beheer**op Label toepassen op items in deze lijst of **bibliotheek**. Als deze optie niet wordt weergegeven, worden uw bewaarlabels nog niet gepubliceerd. Probeer deze stap op een later tijdstip.
    
4. Selecteer In **Label Instellingen toepassen**de optie **Gevoelig** in de vervolgkeuzelijst en klik op **Opslaan**.

Maak vervolgens een nieuw document op de site SensitiveFiles en wijzighet bewaarlabel.
    
1. Klik in de map documenten op **Nieuw > Word-document**.
    
2. Typ tekst in het lege document. Wacht tot de tekst is opgeslagen.
    
3. Klik in de menubalk op **Gedeelde documenten**.
    
4. Klik op de verticale ellips naast de bestandsnaam **Document.docx** en klik vervolgens op **Details**.
    
5. Houd er in het rechterdeelvenster in de sectie **Eigenschappen** onder **Bewaarlabel Bewaar toepassing**op op dat het label **Gevoelige** bewaaring automatisch is toegepast.
    
6. Klik **op Alles bewerken**.
    
7. Selecteer in het deelvenster **Document.docx** onder **Bewaarlabel Toepassen**het label **Zeer vertrouwelijk** en klik op **Opslaan**.

Zie de [stap Classificatie configureren voor uw omgeving](infoprotect-configure-classification.md) in de fase **Informatiebeveiliging** voor informatie en koppelingen voor het implementeren van Office 365-bewaarlabels in productie.

## <a name="next-step"></a>Volgende stap

Ontdek aanvullende functies en mogelijkheden voor [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise Test Lab-handleidingen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise implementeren](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)

 
