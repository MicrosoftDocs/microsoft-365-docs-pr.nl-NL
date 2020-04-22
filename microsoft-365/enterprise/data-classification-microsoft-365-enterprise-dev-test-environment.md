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
description: Gebruik deze Test Lab Guide om bewaarlabels te maken en te gebruiken op documenten in uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: 41873eba8f2d6168d68d771c6feb17a44c775f6a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636090"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Gegevensclassificatie voor uw Microsoft 365 Enterprise-testomgeving

*Deze testlabrichtlijnen kunnen worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*

Met de instructies in dit artikel configureert u gegevensclassificatie met bewaarlabels in uw Microsoft 365 Enterprise-testomgeving.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u alleen bewaarlabels op een lichtgewicht manier wilt configureren met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u bewaarlabels in een gesimuleerde onderneming wilt configureren, volgt u de instructies in [pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van bewaarlabels is geen gesimuleerde bedrijfstestomgeving vereist, die een gesimuleerd intranet bevat dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als optie verstrekt, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 

## <a name="phase-2-create-retention-labels"></a>Fase 2: Bewaarlabels maken

In deze fase maakt u de bewaarlabels voor de verschillende retentieniveaus voor SharePoint Online-documentenmappen.

1. Meld u aan bij het [Microsoft 365-beveiligingscentrum](https://security.microsoft.com/homepage) met uw wereldwijde beheerdersaccount.
    
2. Klik op het **tabblad Start - Microsoft 365** van uw browser op Labels classificatie > **behouden**.
    
3. Klik op **een label maken**.
    
4. Typ In het deelvenster **Naam van uw label** de tekst Intern **openbaar** in Naam van **uw label**en klik op **Volgende**.

5. Klik in het deelvenster **Beschrijvingen van bestandsplannen** op **Volgende**.
    
6. Stel in het deelvenster **Labelinstellingen** indien nodig **Retentie** in **op Aan**en klik op **Volgende**.
    
7. Klik **in** het deelvenster Instellingen controleren op **Het label maken**.
    
8. Herhaal stap 3-7 voor extra labels met deze namen:
    
  - Privé
    
  - Gevoelig
    
  - Zeer vertrouwelijk
  
9. Klik in het deelvenster **Bewaarlabels** op **Labels publiceren**.
    
10. Klik **in** het deelvenster Labels kiezen om te publiceren op Labels kiezen om te **publiceren**.
    
11. Klik **in** het deelvenster Labels kiezen op **Toevoegen** en selecteer alle vier de labels.
    
12. Klik **op Toevoegen**en klik vervolgens op **Gereed.**
    
13. Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.
    
14. Klik in het deelvenster **Locaties kiezen** op **Volgende**.
    
15. Typ in het deelvenster **Uw beleid een naam geven** **Voorbeeldorganisatie** in **Naam** en klik vervolgens op **Volgende**.
    
16. Klik in het deelvenster **Instellingen controleren** op **Labels publiceren**.
 
Houd er rekening mee dat het enkele minuten kan duren voordat de bewaarlabels zijn gepubliceerd.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: Bewaarlabels toepassen op documenten

In deze fase ontdekt u het standaardlabelgedrag voor bestanden in de map Documenten van een SharePoint Online-site en wijzigt u handmatig het bewaarlabel van een document.

Maak eerst een SharePoint Online-teamsite op gevoelig niveau:
  
1. Meld u met een privé-exemplaar van uw browser aan bij de [Office 365-portal](https://portal.office.com) met uw globale beheerdersaccount.
    
2. Klik in de lijst met tegels op **SharePoint**.
    
3. Klik op het nieuwe **tabblad SharePoint** in uw browser op **Site maken**.
    
4. Klik op de pagina **Site maken** op **Teamsite**.
    
5. Typ **Gevoelige bestanden**in **teamsitenaam**.
    
6. Typ **SharePoint-site voor gevoelige bestanden**in **teamsitebeschrijving**.
    
7.  Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.
    
8. Klik in het deelvenster Wie wilt **Finish** **u toevoegen?**
    
Configureer vervolgens de map Documenten van de teamsite SensitiveFiles voor het label Gevoelige bewaaropslag.
  
1. Klik op het tabblad **SensitiveFiles** van uw browser op **Documenten**.
    
2. Klik op het pictogram Instellingen en vervolgens op **Bibliotheekinstellingen**.
    
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

Zie de [stap Classificatie configureren voor uw omgeving](infoprotect-configure-classification.md) in de fase **Informatiebeveiliging** voor informatie en koppelingen naar het implementeren van bewaarlabels in productie.

## <a name="next-step"></a>Volgende stap

Ontdek aanvullende functies en mogelijkheden voor [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise implementeren](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)

 
