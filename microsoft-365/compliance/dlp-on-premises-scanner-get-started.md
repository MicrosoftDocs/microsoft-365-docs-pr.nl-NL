---
title: Aan de slag met de Microsoft 365 preventie van gegevensverlies on-premises scanner (preview)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Stel Microsoft 365 preventie van gegevensverlies on-premises scanner
ms.openlocfilehash: 0390ac48b351b30b75109a3e3a5d18c80847c9d2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289197"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a>Aan de slag met de preventie van gegevensverlies on-premises scanner (preview)

In dit artikel worden de vereisten en configuratie voor de on-premises scanner voor preventie van gegevensverlies van Microsoft 365 beschreven.

## <a name="before-you-begin"></a>Voordat u begint

### <a name="skusubscriptions-licensing"></a>SKU/abonnementenlicenties

Voordat u aan de slag gaat met DLP on-premises scanner, moet u uw [abonnement op Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) en eventuele invoegtoepassingen bevestigen. Als u wilt deelnemen aan de preview-versie, moet aan het beheerdersaccount waarin de DLP-regels worden gemaakt, een van de volgende licenties worden toegewezen:

- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 Information Protection & Governance 


Zie [Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) voor volledige details over licenties

### <a name="permissions"></a>Machtigingen


Gegevens van DL -on-premises scanners kunnen worden weergegeven in [Activity Explorer](data-classification-activity-explorer.md). Er zijn vier rollen die machtigingen verlenen aan Activiteitenverkenner. Het account dat u gebruikt voor het openen van de gegevens, moet lid zijn van een van deze rollen.

- Globale beheerder
- Beheerder voor naleving
- Beveiligingsbeheerder
- Beheerder van nalevingsgegevens

### <a name="dlp-on-premises-scanner-prerequisites"></a>Vereisten van on-premises DLP-scanner

- De AIP-scanner (Azure Information Protection) implementeert overeenkomsten met het DLP-beleid en beleidshandhaving. De scanner is geïnstalleerd als onderdeel van de AIP-client, zodat uw installatie moet voldoen aan alle vereisten voor AIP, de AIP-client en de geïntegreerde labelingsscanner AIP.
- Implementeer de AIP-client en -scanner. [Installeer de geïntegreerde AIP-labelingclient](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) en [], en raadpleeg [Configureren en installeren van de geïntegreerde labelscanner van Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install) voor meer informatie.
- Er moet ten minste één label en beleid in de tenant zijn gepubliceerd, zelfs als alle detectieregels alleen zijn gebaseerd op vertrouwelijke informatietypen.

## <a name="deploy-the-dlp-on-premises-scanner"></a>Implementeer de DLP on-premises scanner

1. Volg de procedures in [AIP-client voor geïntegreerde labeling installeren](/azure/information-protection/rms-client/install-unifiedlabelingclient-app). 
2. Volg de procedures in [Configureren en installeren van de geïntegreerde labelscanner van Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install) om de installatie van de scanner te voltooien.
    1. Configuratie van netwerkdetectietaken is een optionele stap. U kunt dit overslaan en specifieke opslagplaatsen definiëren die moeten worden gescand in uw inhoudsscan.
    2. U moet een inhoudsscantaak maken en de opslagplaatsen opgeven die als host dienen voor de bestanden die door de DLP-engine moeten worden geëvalueerd.
    3. Schakel DLP-regels in voor de gemaakte inhoudsscan of stel de optie **Afdwingen** in op **Uit**, tenzij u rechtstreeks wilt doorgaan naar de fase van het afdwingen van DLP.
3. Controleer of uw inhoudsscantaak aan het juiste cluster is toegewezen. Als u nog steeds geen inhoudsscan hebt gemaakt, maakt u een nieuwe taak en wijst u deze toe aan het cluster met de scannerknooppunten die de openbare preview-versie uitvoeren.

4. Maak verbinding met de [Azure Information Protection-extensie in het Azure-portaal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) en voeg uw opslagplaatsen toe aan de inhoudsscantaak die de scan gaat uitvoeren.

5. Voer een van de volgende handelingen uit als u een scan wilt uitvoeren:
    1. het scannerschema instellen
    1. de optie **Nu scannen** in de handleiding in het portaal gebruiken
    1. of **Start-AIPScan** PowerShell-cmdlet uitvoeren

   > [!IMPORTANT]
   > De scanner voert standaard een deltascan van de opslagplaats uit en de bestanden die al zijn gescand in de vorige scancyclus, worden overgeslagen tenzij het bestand is gewijzigd, of indien u een volledige scan hebt gestart. Volledige herscan kan worden gestart met de optie **Alle bestanden opnieuw scannen** in de gebruikersinterface of door **Start-AIPScan-Reset** uit te voeren.

6.  Ga in het Microsoft 365-compliancecentrum naar de pagina [Preventie van gegevensverlies](https://compliance.microsoft.com/datalossprevention?viewid=policies).

7. Kies **Beleid maken** en maak een DLP-testbeleid. Zie [een DLP-beleid maken op basis van een sjabloon](create-a-dlp-policy-from-a-template.md) als u hulp nodig hebt bij het maken van een beleid. Voer de test uit totdat u vertrouwd bent met deze functie. Gebruik deze parameters voor uw beleid:
    1. Breid het vereik van de DLP-regel voor on-premises scanners zo nodig uit naar specifieke locaties. Als u het bereik **locaties** beperkt tot **Alle**, worden alle bestanden die met de scanner worden gescand, onderworpen aan de DLP-regelaanpassing en -afdwinging.
    1. Wanneer u de locaties opgeeft, kunt u een uitsluitings- of inclusielijst gebruiken. Tijdens een openbare preview kunt u ze niet beide instellen. U kunt definiëren dat de regel alleen relevant is voor paden die overeenkomen met een van de vermelde patronen in de inclusielijst of, alle bestanden, behalve de bestanden die overeenkomen met het patroon dat wordt weergegeven in de inclusielijst. Er worden geen lokale paden ondersteund. Hier ziet u een aantal voorbeelden van geldige paden:
      - \\\server\share
      - \\\server\share\folder1\subfolderabc
      - \*\\folder1
      - \*secret\*.docx
      - \*secret\*.\*
      - https:// sp2010.local/sites/HR
      - https://\*/HR 
    3. Hier zijn enkele voorbeelden van onaanvaardbaar gebruik van waarden:
      - \*
      - \*\\a
      - Aaa
      - c:\
      - C:\test

> [!IMPORTANT]
> De lijst met uitsluitingen heeft voorrang op de inclusielijst.

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a>DLP-waarschuwingen voor on-premises scanners voor weergeven in het dashboard DLP-waarschuwingenbeheer

1. Ga in het Microsoft 365-compliancecentrum naar de [pagina Preventie van gegevensverlies](https://compliance.microsoft.com/datalossprevention?viewid=policies) en kies **Waarschuwingen**.

2. Raadpleeg de procedures in [Informatie over het configureren en weergeven van waarschuwingen voor uw DLP-beleid](dlp-configure-view-alerts-policies.md) om waarschuwingen voor uw DLP-beleid voor eindpunten weer te geven.

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a>DLP on-premises scanner weergeven in Activity Explorer en auditlogboek

> [!NOTE]
> Voor de on-premises scanner moet controle zijn ingeschakeld. In Microsoft 365 is de controle standaard ingeschakeld.

1. Open de [pagina Gegevensclassificatie voor](https://compliance.microsoft.com/dataclassification?viewid=overview) uw domein in het Microsoft 365-compliancecentrum en kies Activiteitenverkenner.

2. Raadpleeg de procedures in [Aan de slag met Activiteitenverkenner](data-classification-activity-explorer.md) om alle gegevens voor uw on-premises scannerlocaties weer te geven en te filteren.

3. Open in het [auditlogboek in het compliancecentrum](https://security.microsoft.com/auditlogsearch). Tijdens de openbare preview zijn de DLP-regelovereenkomsten ook beschikbaar in de gebruikersinterface van het auditlogboek of beschikbaar door [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell. 


## <a name="next-steps"></a>Volgende stappen
Nu u een testbeleid heeft ge*implementeerd voor DLP on-premises locaties en de activiteitsgegevens kunt bekijken in Activiteitenverkenner, kunt u verder gaan met de volgende stap, waarin u DLP-beleid maakt voor het beveiligen van uw gevoelige items.

- [DLP on-premises gebruiken (preview)](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>Zie ook

- [Meer informatie over DLP-on-premises scanner (preview)](dlp-on-premises-scanner-learn.md)
- [DLP-on-premises scanner gebruiken (preview)](dlp-on-premises-scanner-use.md)
- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)
- [Een DLP-beleid maken, testen en afstemmen](create-test-tune-dlp-policy.md)
- [Aan de slag met Activity Explorer](data-classification-activity-explorer.md)
- [Microsoft 365-abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)