---
title: Gebruik Microsoft 365 preventie van gegevensverlies on-premises scanner (preview)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
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
description: Lees hoe u met de preventie van gegevensverlies in Microsoft 365 op een on-premises scanner data-at-rest kunt scannen en beschermende maatregelen kunt implementeren voor het on-premises delen van bestanden en on-premises SharePoint-mappen en -documentbibliotheken.
ms.openlocfilehash: 0abe36af5588c1828da106779a144b6e7f37d6a8
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162909"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>Gebruik de Microsoft 365 preventie van gegevensverlies on-premises scanner (preview)

Om u vertrouwd te maken met de on-premises functies van DLP en hoe deze worden gebruikt in DLP-beleid, hebben we enkele scenario's opgesteld die u kunt volgen.

> [!IMPORTANT]
> Deze on-premises DLP-scenario's zijn niet de officiële procedures voor het maken en afstemmen van DLP-beleid. Raadpleeg de onderstaande onderwerpen wanneer u in het algemeen met DLP-beleid moet werken:
>- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)
>- [Aan de slag met het standaard DLP-beleid](get-started-with-the-default-dlp-policy.md)
>- [Een DLP-beleid maken vanuit een sjabloon](create-a-dlp-policy-from-a-template.md)
>- [Een DLP-beleid maken, testen en afstemmen](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a>Scenario: Ontdek bestanden die overeenkomen met DLP-regels

Gegevens van DLP-on-premises scanner komen in verschillende gebieden voor

#### <a name="activity-explorer"></a>Activiteitenverkenner

 Microsoft DLP voor on-premises detecteert DLP-regelovereenkomsten en rapporteert deze aan [Activiteitenverkenner](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer). 
 
#### <a name="microsoft-365-audit-log"></a>Microsoft 365-auditlogboek

Tijdens de openbare preview zijn de DLP-regelovereenkomsten ook beschikbaar in de gebruikersinterface van het auditlogboek. Zie [Het auditlogboek zoeken in het compliancecentrum](search-the-audit-log-in-security-and-compliance.md)  of beschikbaar door [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell.

#### <a name="aip"></a>AIP

Detectiegegevens zijn beschikbaar in een lokaal rapport in de CSV-indeling en zijn opgeslagen onder:

**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.

 Zoek de volgende kolommen:
- DLP-modus
- DLP-status
- DLP-opmerking
- DLP-regelnaam DLP-acties
- Eigenaar
- Huidige NTFS-machtigingen (SDDL)
- Toegepaste NTFS-machtigingen (SDDL)
- Type NTFS-machtigingen
 
### <a name="scenario-enforce-dlp-rule"></a>Scenario: DLP-regel afdwingen 

Als u DLP-regels wilt afdwingen voor de gescande bestanden, moet afdwingen zijn ingeschakeld op zowel de inhoudsscantaak in AIP als op het beleidsniveau in DLP.


#### <a name="configure-dlp-to-enforce-policy-actions"></a>DLP configureren voor het afdwingen van beleidsacties

1. Open de [pagina voor preventie van gegevensverlies](https://compliance.microsoft.com/datalossprevention?viewid=policies) en selecteer het DLP-beleid dat is gericht op de on-premises locatie-opslagplaatsen die u in AIP hebt geconfigureerd. 
2. Geef het beleid een naam.
3. Selecteer op de pagina **Het beleid testen of inschakelen****Ja en schakel het meteen in**. 

## <a name="see-also"></a>Zie ook

- [Meer informatie over DLP-on-premises scanner (preview)](dlp-on-premises-scanner-learn.md)
- [Aan de slag met DLP-on-premises scanner (preview)](dlp-on-premises-scanner-get-started.md)
- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)
- [Een DLP-beleid maken, testen en afstemmen](create-test-tune-dlp-policy.md)
- [Aan de slag met de Activiteitenverkenner](data-classification-activity-explorer.md)