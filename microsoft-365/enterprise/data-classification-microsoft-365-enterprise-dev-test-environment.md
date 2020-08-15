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
ms.openlocfilehash: 171fcb74b09a1f2e5c80f23e010640dce55660bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686404"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Gegevensclassificatie voor uw Microsoft 365-testomgeving voor ondernemingen

*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*

Met de instructies in dit artikel configureert u de gegevensclassificatie met behulp van labels voor bewaarbeleid in uw Microsoft 365 voor Enterprise-testomgeving.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u alleen Bewaar etiketten op een lichte manier wilt configureren met de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u de Bewaar labels van een gesimuleerde Enterprise-organisatie wilt configureren, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van labels voor bewaarbeleid is de gesimuleerde Enterprise-testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. U kunt dit hier opgeven als optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt. 

## <a name="phase-2-create-retention-labels"></a>Fase 2: Labels voor bewaarbeleid maken

In deze fase maakt u de labels voor bewaarbeleid voor de verschillende niveaus voorbehoud van mappen in SharePoint Online-documenten.

1. Meld u aan bij het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/homepage) met uw globale beheerdersaccount.
    
2. Klik op het tabblad **Start-Microsoft 365-beveiliging** van uw browser op **classificatie > Bewaar etiketten**.
    
3. Klik op **een label maken**.
    
4. In het deelvenster **naam van uw etiket** typt u **intern openbaar** in **naam van uw etiket**en klikt u op **volgende**.

5. Klik in het deelvenster met **descriptors voor bestands planning** op **volgende**.
    
6. Stel in het deelvenster **etiketinstellingen** , indien nodig, **bewaren** in **op**aan en klik vervolgens op **volgende**.
    
7. Klik in het deelvenster **uw instellingen controleren** op **het etiket maken**.
    
8. Herhaal stappen 3-7 voor aanvullende labels met de volgende namen:
    
  - Privé
    
  - Gevoelig
    
  - Zeer vertrouwelijk
  
9. Klik in het deelvenster **Bewaar labels** op **etiketten publiceren**.
    
10. Klik in het deelvenster **Kies Labels om te publiceren** op **etiketten selecteren om te publiceren**.
    
11. Klik in het deelvenster **labels kiezen** op **toevoegen** en selecteer alle vier de etiketten.
    
12. Klik op **Toevoegen** en klik op **Gereed**.
    
13. Klik in het deelvenster **Labels kiezen om te publiceren** op **Volgende**.
    
14. Klik in het deelvenster **Locaties kiezen** op **Volgende**.
    
15. Typ in het deelvenster **Uw beleid een naam geven** **Voorbeeldorganisatie** in **Naam** en klik vervolgens op **Volgende**.
    
16. Klik in het deelvenster **uw instellingen controleren** op **etiketten publiceren**.
 
Het kan een paar minuten duren voordat de Bewaar etiketten zijn gepubliceerd.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: Labels voor bewaarbeleid toepassen op documenten

In deze fase ontdekt u het standaardgedrag van het Bewaar label voor bestanden in de map documenten van een SharePoint Online-site en wijzigt u het Bewaar label van een document handmatig.

Maak eerst een SharePoint Online-team site met gevoelige niveaus:
  
1. Meld u met een persoonlijk exemplaar van uw browser aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) met uw globale beheerdersaccount.
    
2. Klik in de lijst met tegels op **SharePoint**.
    
3. Klik op het tabblad nieuwe **SharePoint** in uw browser op **site maken**.
    
4. Klik op de pagina **Site maken** op **Teamsite**.
    
5. Typ **SensitiveFiles**in de naam van de **team site**.
    
6. Typ in een beschrijving van de **team site**de **SharePoint-site voor gevoelige bestanden**.
    
7.  Selecteer bij **Privacy-instellingen** de optie **Privé: alleen leden hebben toegang tot deze site** en klik vervolgens op **Volgende**.
    
8. Klik in het deelvenster **personen die u wilt toevoegen** op **Voltooien**.
    
Vervolgens configureert u de map documenten van de team site van SensitiveFiles voor het gevoelige Bewaar label.
  
1. Klik op het tabblad **SensitiveFiles** van uw browser op **documenten**.
    
2. Klik op het instellingenpictogram en vervolgens op **Bibliotheekinstellingen**.
    
3. Klik onder **machtigingen en beheer**op **label toepassen op items in deze lijst of bibliotheek**. Als deze optie niet wordt weergegeven, zijn uw Bewaar etiketten nog niet gepubliceerd. Probeer deze stap later nog eens.
    
4. Selecteer in de vervolgkeuzelijst **instellingen-labels toepassen**de optie **gevoelig** en klik vervolgens op **Opslaan**.

Vervolgens maakt u een nieuw document op de site van SensitiveFiles en wijzigt u het Bewaar label.
    
1. Klik in de map documenten op **nieuw > Word-document**.
    
2. Typ wat tekst in het lege document. Wacht totdat de tekst is opgeslagen.
    
3. Klik op de menubalk op **gedeelde documenten**.
    
4. Klik op de drie puntjes naast de naam van het **Document.docx** -bestand en klik vervolgens op **Details**.
    
5. In het deelvenster aan de rechterkant, in de sectie **Eigenschappen** , onder **Bewaar label toepassen**, is het **gevoelige** Bewaar label automatisch toegepast op het document.
    
6. Klik op **Alles bewerken**.
    
7. Selecteer in het deelvenster **Document.docx** , onder **Bewaar etiket toepassen**, de optie voor **zeer vertrouwelijke** etiketten en klik vervolgens op **Opslaan**.

## <a name="next-step"></a>Volgende stap

Verken de functies en mogelijkheden van extra [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

 
