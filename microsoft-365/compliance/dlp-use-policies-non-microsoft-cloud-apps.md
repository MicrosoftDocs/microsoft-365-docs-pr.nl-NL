---
title: Preventiebeleid voor gegevensverlies gebruiken voor niet-Microsoft-cloud-apps
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het gebruik van dlp-beleid voor niet-Microsoft-cloud-apps.
ms.openlocfilehash: fbba87fc5bb3bbca7e67ba374e202098a22f4a5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300122"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>Beleid voor preventie van gegevensverlies gebruiken voor niet-Microsoft-cloud-apps (preview)

DLP-beleid (Data Loss Prevention) voor niet-Microsoft-cloud-apps maakt deel uit van de Microsoft 365 DLP-suite met functies; met behulp van deze functies kunt u gevoelige items ontdekken en beveiligen in Microsoft 365 services. Zie Meer informatie over preventie van gegevensverlies voor meer informatie over alle Microsoft [DLP-aanbiedingen.](dlp-learn-about-dlp.md)

U kunt DLP-beleid gebruiken om niet-Microsoft-cloud-apps te controleren en te detecteren wanneer gevoelige items worden gebruikt en gedeeld via niet-Microsoft-cloud-apps. Als u dit beleid gebruikt, hebt u de zichtbaarheid en controle die u nodig hebt om ervoor te zorgen dat ze correct worden gebruikt en beveiligd, en voorkomt u risicovol gedrag dat hen in gevaar kan brengen.

## <a name="before-you-begin"></a>Voordat u begint

### <a name="skusubscriptions-licensing"></a>SKU/abonnementenlicenties

Voordat u DLP-beleid gaat gebruiken voor niet-Microsoft-cloud-apps, bevestigt u uw Microsoft 365 [en](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) eventuele invoegtoepassingen. Als u deze functionaliteit wilt openen en gebruiken, moet u een van deze abonnementen of invoegtoepassingen hebben:

- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 Security

### <a name="permissions"></a>Machtigingen
De gebruiker die het DLP-beleid maakt, moet het volgende doen:
- Globale beheerder
- Beheerder voor naleving
- Beheerder van nalevingsgegevens

### <a name="prepare-your-cloud-app-security-environment"></a>Uw Cloud App Security voorbereiden

DLP-beleid voor niet-Microsoft-cloud-apps gebruikt Cloud App Security DLP-mogelijkheden. Als u het wilt gebruiken, moet u uw Cloud App Security voorbereiden. Zie Direct zichtbaarheids-, beveiligings- en beheeracties instellen voor [uw apps voor instructies.](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)

### <a name="connect-a-non-microsoft-cloud-app"></a>Verbinding maken een niet-Microsoft-cloud-app

Als u DLP-beleid wilt gebruiken voor een specifieke niet-Microsoft-cloud-app, moet de app zijn verbonden met Cloud App Security. Zie voor meer informatie:

- [Verbinding maken Vak](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [Verbinding maken Dropbox](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [Verbinding maken G-Suite](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [Verbinding maken Salesforce](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [Verbinding maken Cisco Webex](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

Nadat u uw cloud-apps hebt verbonden met Cloud App Security, kunt u Microsoft 365 DLP-beleid voor hen maken.

> [!NOTE]
> Het is ook mogelijk om DLP-Microsoft Cloud App Security te maken voor Microsoft-cloud-apps. U wordt echter aangeraden om DLP-Microsoft 365 te gebruiken voor het maken en beheren van DLP-beleid voor Microsoft-cloud-apps.

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>Een DLP-beleid maken voor een niet-Microsoft-cloud-app

Wanneer u een locatie voor het DLP-beleid selecteert, zet u de **Microsoft Cloud App Security** in.

- Als u een specifieke app of exemplaar wilt selecteren, selecteert u **Exemplaar kiezen.**
- Als u geen exemplaar selecteert, worden in het beleid alle verbonden apps in uw Microsoft Cloud App Security gebruikt.

   ![Locaties om het beleid toe te passen](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US en Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

U kunt verschillende acties kiezen voor elke ondersteunde niet-Microsoft-cloud-app. Voor elke app zijn er verschillende mogelijke acties (afhankelijk van de CLOUD-app-API).

![Regel maken](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

Wanneer u een regel maakt in het DLP-beleid, kunt u een actie selecteren voor niet-Microsoft-cloud-apps. Als u apps van derden wilt beperken, **selecteert u Apps van derden beperken.**

![Apps van derden beperken](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> DLP-beleid dat is toegepast op niet-Microsoft-apps Microsoft Cloud App Security. Wanneer het DLP-beleid voor een niet-Microsoft-app wordt gemaakt, wordt automatisch hetzelfde beleid gemaakt in Microsoft Cloud App Security.

Zie Een DLP-beleid maken en afstemmen voor informatie over het maken en configureren van [DLP-beleid.](./create-test-tune-dlp-policy.md)

## <a name="see-also"></a>Zie ook

- [Test maken en een DLP-beleid afstemmen](./create-test-tune-dlp-policy.md)
- [Aan de slag met het standaard DLP-beleid](./get-started-with-the-default-dlp-policy.md)
- [Een DLP-beleid maken vanuit een sjabloon](./create-a-dlp-policy-from-a-template.md)
