---
title: Verbeterde Microsoft 365-beveiliging voor uw Microsoft 365 voor Enterprise testomgeving
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
description: Gebruik deze test lab-handleiding voor het inschakelen van extra Microsoft 365-beveiligingsinstellingen voor uw Microsoft 365 voor Enterprise test omgeving.
ms.openlocfilehash: 09a613261bc173cd71e9cc2dd58a32a9547ece21
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398947"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Verbeterde Microsoft 365-beveiliging voor uw Microsoft 365 voor Enterprise testomgeving

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

Aan de hand van de instructies in dit artikel configureert u aanvullende instellingen voor Microsoft 365 om de beveiliging in uw Microsoft 365 voor Enterprise testomgeving te verbeteren.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u de beveiliging voor Microsoft 365 slechts op een lichte manier met de minimumvereisten wilt configureren, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u een verbeterde Microsoft 365-beveiliging in een gesimuleerde onderneming wilt configureren, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van de beveiliging van Microsoft 365 is de gesimuleerde Enterprise-testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. U kunt dit hier opgeven als optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fase 2: verbeterde Microsoft 365-beveiliging configureren

In deze fase schakelt u de verbeterde Microsoft 365-beveiliging in voor uw Microsoft 365 voor Enterprise testomgeving. Zie voor meer informatie en instellingen [uw Tenant configureren voor een betere beveiliging](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>SharePoint Online configureren voor het blokkeren van apps die moderne verificatie niet ondersteunen

Voor apps waarvoor geen ondersteuning biedt voor moderne verificatie, gelden geen [identiteits-en Apparaattoegang-configuraties](../security/office-365-security/microsoft-365-policies-configurations.md) , wat een belangrijk element is van het beveiligen van uw microsoft 365-abonnement en de bijbehorende digitale activa. 

1. Ga naar het Microsoft 365-Beheercentrum ( [https://portal.microsoft.com](https://portal.microsoft.com) ) en meld u aan bij uw Microsoft 365-test abonnement met uw globale beheerdersaccount.
    
  - Als u de testomgeving lichtgewicht Microsoft 365 gebruikt, meldt u zich aan bij uw lokale computer.
    
  - Als u de gesimuleerde Enterprise Microsoft 365 testomgeving gebruikt, kunt u de [Azure-Portal](https://portal.azure.com) gebruiken om verbinding te maken met de virtuele computer van CLIENT1 en vervolgens aan te melden bij CLIENT1.
 
2. Klik op het nieuwe **Microsoft 365-Beheercentrum** , onder **beheer centra** in het linker navigatiedeelvenster, op **SharePoint**.
3. Klik op het tabblad nieuw **SharePoint-Beheercentrum** op **beleids > toegangsbeheer**.
4. Klik op **apps die moderne verificatie niet ondersteunen**, selecteer **toegang blokkeren**en klik op **Opslaan**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Geavanceerde Bedreigingsbeveiliging inschakelen voor SharePoint, OneDrive voor bedrijven en Microsoft teams

Office 365 Advanced Threat Protection (ATP) voor SharePoint, OneDrive en Microsoft teams beschermt uw organisatie per ongeluk om kwaadaardige bestanden te delen.

1. Ga naar de [beveiligings & nalevings centrum](https://protection.office.com) en meld u aan met uw globale beheerdersaccount.

2. Klik in het linker navigatiedeelvenster onder **bedreigings beheer**op **beleidsregels**en klik vervolgens op **veilige bijlagen voor ATP**. 

3. Onder **bestanden beschermen in SharePoint, OneDrive en Microsoft teams**. Selecteer **ATP inschakelen voor SharePoint, OneDrive en Microsoft teams**.

4. Klik op **Opslaan**.


### <a name="enable-anti-malware"></a>Schakel anti malware in

Malware is samengesteld uit virussen en spyware. Virussen infecteren andere Programma's en gegevens, en de personen die op de computer worden verspreid, op zoek naar Programma's. Spyware verwijst naar malware waarmee uw persoonlijke gegevens worden verzameld, zoals aanmeldingsgegevens en persoonlijke gegevens, en stuurt u de malware vervolgens terug naar de auteur van de malware. 

Microsoft 365 heeft ingebouwde functies voor het filteren van malware en spam en helpt inkomende en uitgaande berichten van schadelijke software te beschermen en u te helpen beschermen tegen ongewenste e-mail. Zie [antispam & bescherming tegen malware](../security/office-365-security/anti-spam-and-anti-malware-protection.md)voor meer informatie.

U kunt als volgt controleren of de verwerking van schadelijke software wordt uitgevoerd voor bestanden met veelgebruikte bestandstypen voor bijlagen:

1. Klik op de knop terug in uw browser om terug te gaan naar de pagina **beleid** .
2. Klik op **anti malware**.
3. Dubbelklik op het beleid met de naam **standaard**.
4. Klik in het venster **anti-malwarebeleid** op **instellingen**.
4. Selecteer onder **algemene typen bijlagen**de optie **aan**en klik vervolgens op **Opslaan**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fase 3: het beveiligings dashboard onderzoeken

Met behulp van risicobeheer in Microsoft 365 kunt u de toegang tot de gegevens van uw organisatie beheren en beheren, uw organisatie beschermen tegen gegevensverlies en inkomende en uitgaande berichten beschermen tegen schadelijke software en spam. U kunt ook risicobeheer gebruiken om de reputatie van uw domein te beschermen en te bepalen of een van de afzenders schadelijk accounts zijn van uw domein. 

Het beveiligings dashboard weergeven:

1. Ga zo nodig naar de [beveiligings & nalevings centrum](https://protection.office.com) en meld u aan met uw globale beheerdersaccount.

2. Klik in het linker navigatiedeelvenster onder **Threat Management**op **Dashboard**.

Neem contact op met alle kaarten op het dashboard om uzelf vertrouwd te maken met de verstrekte informatie.

Zie voor meer informatie het [beveiligings dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).


## <a name="phase-4-examine-microsoft-secure-score"></a>Fase 4: Microsoft Secure Score bestuderen

Secure Score van Microsoft toont uw beveiligings-Posture als een getal, dat uw huidige niveau aangeeft ten opzichte van de functies die beschikbaar zijn in uw abonnement. U hebt ook een lijst met verduidelijkings acties die u kunt ondernemen om de score te verbeteren.

1. Maak een nieuw tabblad in uw browser en ga naar het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/)en klik op **Secure Score**.
2. Op het tabblad **overzicht**  kunt u uw huidige beveiligde Score en de manier waarop deze worden vergeleken met het algemene gemiddelde en de abonnementen met een vergelijkbaar aantal licenties.
3. Lees in de lijst met acties op het tabblad **kwaliteits verbeteringen** de actie die u kunt uitvoeren om de score te verhogen.

Zie [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

Verken de functies en mogelijkheden van extra [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
