---
title: Verhoogde Microsoft 365-beveiliging voor uw Microsoft 365 Enterprise-testomgeving
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
description: Gebruik deze Test Lab Guide om extra Microsoft 365-beveiligingsinstellingen in te schakelen in uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: 465e9df40e8dfe9883a81d352eabff17151df8f3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805267"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Verhoogde Microsoft 365-beveiliging voor uw Microsoft 365 Enterprise-testomgeving

*Deze Test Lab Guide kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*

Met de instructies in dit artikel configureert u extra Microsoft 365-instellingen om de beveiliging in uw Microsoft 365 Enterprise-testomgeving te verhogen.

![Test Lab-hulplijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u alleen de verhoogde Microsoft 365-beveiliging op een lichtgewicht manier wilt configureren met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u verhoogde Microsoft 365-beveiliging in een gesimuleerde onderneming wilt configureren, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Het testen van verhoogde Microsoft 365-beveiliging vereist niet de gesimuleerde bedrijfstestomgeving, die een gesimuleerd intranet bevat dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als optie geleverd, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: Microsoft 365-beveiliging configureren

In deze fase schakelt u verhoogde Microsoft 365-beveiliging in voor uw Microsoft 365 Enterprise-testomgeving. Zie [Uw Office 365-tenant configureren voor meer beveiliging](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)voor meer informatie en instellingen.

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>SharePoint Online configureren om apps te blokkeren die geen ondersteuning bieden voor moderne verificatie

Apps die geen moderne verificatie ondersteunen, kunnen geen [configuratie voor identiteits- en apparaattoegang](microsoft-365-policies-configurations.md) op hen toepassen, wat een belangrijk element is voor het beveiligen van uw Microsoft 365-abonnement en de digitale assets ervan. 

1. Ga naar het Microsoft 365-beheercentrum[https://portal.microsoft.com](https://portal.microsoft.com)en meld u aan bij uw Microsoft 365-testlababonnement met uw wereldwijde beheerdersaccount.
    
  - Als u de lichtgewicht Microsoft 365-testomgeving gebruikt, meldt u zich aan vanaf uw lokale computer.
    
  - Als u de gesimuleerde microsoft 365-testomgeving voor bedrijven gebruikt, gebruikt u de [Azure-portal](https://portal.azure.com) om verbinding te maken met de client1-virtuele machine en meldt u zich aan bij CLIENT1.
 
2. Klik op het nieuwe tabblad **Microsoft 365-beheercentrum** onder **Beheercentra** in het linkernavigatiedeelvenster op **SharePoint**.
3. Klik op het nieuwe tabblad **SharePoint-beheercentrum** op **Toegangsbeheer**.
4. Klik op **Apps die geen moderne verificatie ondersteunen,** selecteer Toegang **blokkeren**en klik vervolgens op **Opslaan**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Geavanceerde bedreigingsbeveiliging inschakelen voor SharePoint, OneDrive voor Bedrijven en Microsoft Teams

Office 365 Advanced Threat Protection (ATP) voor SharePoint, OneDrive en Microsoft Teams beschermt uw organisatie tegen het per ongeluk delen van schadelijke bestanden.

1. Ga naar het [Office 365 Security & Compliance Center](https://protection.office.com) en meld u aan met uw wereldwijde beheerdersaccount.

2. Klik in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**op **Beleid**en klik vervolgens op **veilige ATP-bijlagen**. 

3. Ga onder **Bestanden beveiligen in SharePoint, OneDrive en Microsoft Teams**. selecteer **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams**.

4. Klik op **Opslaan**.


### <a name="enable-anti-malware"></a>Anti-malware inschakelen

Malware bestaat uit virussen en spyware. Virussen infecteren andere programma's en gegevens, en ze verspreiden zich over uw computer op zoek naar programma's te infecteren. Spyware verwijst naar malware die uw persoonlijke gegevens verzamelt, zoals aanmeldingsgegevens en persoonlijke gegevens, en deze terugstuurt naar de malwareauteur. 

Microsoft 365 heeft ingebouwde mogelijkheden voor malware en spamfilter die binnenkomende en uitgaande berichten beschermen tegen schadelijke software en u helpen beschermen tegen spam. Zie [Anti-spam & bescherming tegen malware in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection) voor meer informatie

Ga als u ervoor zorgen dat de verwerking van malware tegen malware wordt uitgevoerd op bestanden met veelvoorkomende bijlagebestandstypen:

1. Klik op de terugknop in uw browser om terug te gaan naar de pagina **Beleid.**
2. Klik op **Anti-malware**.
3. Dubbelklik op het beleid **met de**naam Standaard .
4. Klik in het beleidsvenster **Anti-malware** op **Instellingen**.
4. Selecteer Onder **Het filter Algemene gehechtheidstypen**de optie **Aan**en klik vervolgens op **Opslaan**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fase 3: Het beveiligingsdashboard onderzoeken

Met Office 365-dreigingsbeheer u de toegang tot de gegevens van uw organisatie beheren en beheren, uw organisatie beschermen tegen gegevensverlies en binnenkomende en uitgaande berichten beschermen tegen schadelijke software en spam. U gebruikt ook bedreigingsbeheer om de reputatie van uw domein te beschermen en om te bepalen of afzenders accounts uit uw domein al dan niet kwaadwillig spoofen. 

Ga als nog eens over het beveiligingsdashboard:

1. Ga indien nodig naar het [Office 365 Security & Compliance Center](https://protection.office.com) en meld u aan met uw globale beheerdersaccount.

2. Klik in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**op **Dashboard**.

Bekijk alle kaarten op het dashboard om vertrouwd te raken met de verstrekte informatie.

Zie [Beveiligingsdashboard voor](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)meer informatie.


## <a name="phase-4-examine-microsoft-secure-score"></a>Fase 4: Microsoft Secure Score onderzoeken

Microsoft Secure Score toont uw beveiligingshouding als een getal, dat uw huidige niveau aangeeft ten opzichte van de functies die beschikbaar zijn in uw abonnement. Het geeft je ook een lijst van verbeteracties die je nemen om je score te verbeteren.

1. Maak een nieuw tabblad in uw browser en ga naar het [Microsoft 365-beveiligingscentrum](https://security.microsoft.com/)en klik vervolgens op **Beveiligde score**.
2. Noteer op het tabblad **Overzicht** uw huidige beveiligde score en hoe deze zich verhoudt tot het algemene gemiddelde en abonnementen met een vergelijkbaar aantal licenties.
3. Lees op het tabblad **Verbeteracties** de lijst met acties die u uitvoeren om uw score te verhogen.

Zie [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

Zie de stap [Extra beveiliging configureren voor Microsoft 365](infoprotect-configure-increased-security-office-365.md) in de fase **Informatiebeveiliging** voor informatie en koppelingen om deze instellingen in productie te configureren.

Ontdek aanvullende functies en mogelijkheden voor [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise Test Lab-handleidingen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise implementeren](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)
