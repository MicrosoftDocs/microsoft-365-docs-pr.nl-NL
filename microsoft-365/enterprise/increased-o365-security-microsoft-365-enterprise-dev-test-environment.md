---
title: Verbeterde microsoft 365-beveiliging voor uw Microsoft 365 voor ondernemingstestomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Gebruik deze testlaboratoriumhandleiding om aanvullende beveiligingsinstellingen van Microsoft 365 in te stellen voor uw Microsoft 365 voor ondernemingstestomgeving.
ms.openlocfilehash: d1bff8b736e5074f621a173d206f7c5f77841b25
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198349"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Verbeterde microsoft 365-beveiliging voor uw Microsoft 365 voor ondernemingstestomgeving

*Deze testlaborator kan alleen worden gebruikt voor Microsoft 365 voor testomgevingen voor ondernemingen.*

Met de instructies in dit artikel configureert u aanvullende Microsoft 365-instellingen om de beveiliging in uw Microsoft 365 voor ondernemingstestomgeving te verhogen.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klik op [Hier](../downloads/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 voor ondernemingstestomgeving opbouwen

Als u alleen de beveiliging van Microsoft 365 op een lichtgewicht manier wilt configureren met de minimumvereisten, volgt u de instructies in [de lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u de beveiliging van Microsoft 365 in een gesimuleerde onderneming wilt verbeteren, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van de verbeterde beveiliging van Microsoft 365 is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: Verbeterde beveiliging van Microsoft 365 configureren

In deze fase kunt u de beveiliging van Microsoft 365 voor uw Microsoft 365-testomgeving voor ondernemingen verbeteren. Zie Uw tenant configureren voor meer beveiliging voor [meer informatie en instellingen.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>SharePoint Online configureren om apps te blokkeren die geen moderne verificatie ondersteunen

Apps die geen ondersteuning bieden voor moderne verificatie, kunnen niet worden toegepast op [identiteits- en apparaattoegangsconfiguraties.](../security/office-365-security/microsoft-365-policies-configurations.md) Dit is een belangrijk onderdeel van het beveiligen van uw Microsoft 365-abonnement en de digitale assets. 

1. Ga naar het Microsoft 365-beheercentrum () en meld u aan bij uw Test lab-abonnement van [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365 met uw globale beheerdersaccount.
    
  - Als u de lichtgewicht Microsoft 365-testomgeving gebruikt, meld u dan aan vanaf uw lokale computer.
    
  - Als u de gesimuleerde microsoft 365-testomgeving voor ondernemingen gebruikt, gebruikt u de [Azure-portal](https://portal.azure.com) om verbinding te maken met de virtuele client1-machine en u vervolgens aan te melden vanaf CLIENT1.
 
2. Klik op het nieuwe **tabblad Microsoft 365-beheercentrum** onder **Beheercentra** in het linkernavigatiedeelvenster op **SharePoint.**
3. Klik op het nieuwe **tabblad SharePoint-beheercentrum** op **Beleid > Access-besturingselement.**
4. Klik **op Apps die geen moderne verificatie ondersteunen,** selecteer Toegang **blokkeren** en klik vervolgens op **Opslaan.**


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Defender inschakelen voor Office 365 voor SharePoint, OneDrive voor Bedrijven en Microsoft Teams

Defender voor Office 365 voor SharePoint, OneDrive en Microsoft Teams beschermt uw organisatie tegen onbedoeld delen van schadelijke bestanden.

1. Ga naar het [Beveiligingscentrum & compliancecentrum](https://protection.office.com) en meld u aan met uw globale beheerdersaccount.

2. Klik in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** op **Beleid** en klik vervolgens **op Veilige bijlagen.** 

3. Onder **Bestanden beveiligen in SharePoint, OneDrive en Microsoft Teams**. selecteer **ATP voor SharePoint, OneDrive en Microsoft Teams in- en uit.**

4. Klik op **Opslaan**.


### <a name="enable-anti-malware"></a>Anti-malware inschakelen

Malware bestaat uit virussen en spyware. Virussen besmetten andere programma's en gegevens en verspreiden zich op uw computer op zoek naar programma's om te infecteren. Spyware verwijst naar malware die uw persoonlijke gegevens verzamelt, zoals aanmeldingsgegevens en persoonlijke gegevens, en stuurt deze terug naar de malwareauteur. 

Microsoft 365 beschikt over ingebouwde mogelijkheden voor malware en spamfilters die binnenkomende en uitgaande berichten helpen beschermen tegen schadelijke software en u helpen beschermen tegen spam. Zie [Anti-spam & anti-malwarebeveiliging](../security/office-365-security/anti-spam-and-anti-malware-protection.md)voor meer informatie.

Als u ervoor wilt zorgen dat anti-malwareverwerking wordt uitgevoerd op bestanden met veelgebruikte bestandstypen voor bijlagen:

1. Klik op de knop Terug in uw browser om terug te gaan naar de **pagina Beleid.**
2. Klik **op Anti-malware.**
3. Dubbelklik op het beleid met de naam **Standaard.**
4. Klik in **het venster Anti-malwarebeleid** op **Instellingen.**
4. Selecteer **onder Gemeenschappelijke bijlagetypen de** optie **Aan** en klik vervolgens op **Opslaan.**


## <a name="phase-3-examine-the-security-dashboard"></a>Fase 3: Het beveiligingsdashboard bekijken

Bedreigingsbeheer in Microsoft 365 kan u helpen de toegang van mobiele apparaten tot de gegevens van uw organisatie te beheren en beheren, uw organisatie te beschermen tegen gegevensverlies en binnenkomende en uitgaande berichten te beschermen tegen schadelijke software en spam. U gebruikt bedreigingsbeheer ook om de reputatie van uw domein te beschermen en om te bepalen of afzenders accounts van uw domein al dan niet met kwaadwillende bedoelingen vervalsen. 

Het beveiligingsdashboard bekijken:

1. Ga indien nodig naar het [Beveiligingscentrum & compliancecentrum](https://protection.office.com) en meld u aan met uw globale beheerdersaccount.

2. Klik in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** op **Dashboard.**

Bekijk alle kaarten op het dashboard om vertrouwd te raken met de verstrekte informatie.

Zie Beveiligingsdashboard [voor meer informatie.](../security/office-365-security/security-dashboard.md)


## <a name="phase-4-examine-microsoft-secure-score"></a>Fase 4: Microsoft Secure Score onderzoeken

Microsoft Secure Score toont uw beveiligingsstatus als een getal, wat uw huidige niveau aangeeft ten opzichte van de functies die beschikbaar zijn in uw abonnement. U krijgt ook een lijst met verbeteracties die u kunt uitvoeren om uw score te verbeteren.

1. Maak een nieuw tabblad in uw browser en ga naar het [Microsoft 365-beveiligingscentrum](https://security.microsoft.com/)en klik vervolgens op **Score beveiligen.**
2. Noteer **op het**  tabblad Overzicht uw huidige Secure Score en hoe deze zich verhoudt tot het globale gemiddelde en abonnementen met een vergelijkbaar aantal licenties.
3. Lees op **het tabblad** Acties voor verbetering de lijst met acties die u kunt uitvoeren om uw score te verhogen.

Zie Microsoft Secure Score voor [meer informatie.](../security/defender/microsoft-secure-score.md)

## <a name="next-steps"></a>Volgende stappen

Ontdek extra [functies en](m365-enterprise-test-lab-guides.md#information-protection) mogelijkheden voor informatiebeveiliging in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)