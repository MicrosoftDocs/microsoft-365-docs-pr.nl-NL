---
title: Microsoft Defender voor Eindpunt integreren met andere Microsoft-oplossingen
description: Lees hoe Microsoft Defender voor Eindpunt integreert met andere Microsoft-oplossingen, waaronder Microsoft Defender voor identiteit en Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender, conditional access, office, Microsoft Defender for Endpoint, microsoft defender for identity, microsoft defender for office, Azure Defender, microsoft cloud app security, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aeb6d93017f138ce898d25f7d76e05cdcf3e90c5
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878566"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender voor Eindpunt en andere Microsoft-oplossingen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>Integreren met andere Microsoft-oplossingen

Microsoft Defender voor Eindpunt wordt rechtstreeks geïntegreerd met verschillende Microsoft-oplossingen.

### <a name="azure-defender"></a>Azure Defender
Microsoft Defender voor Eindpunt biedt een uitgebreide serverbeveiligingsoplossing, eindpuntdetectie en -respons (EDR) mogelijkheden op Windows servers.

### <a name="azure-sentinel"></a>Azure Sentinel
Met de Microsoft Defender voor Eindpunt-connector kunt u waarschuwingen van Microsoft Defender voor Eindpunt streamen naar Azure Sentinel. Op deze manier kunt u beveiligingsgebeurtenissen in uw organisatie uitgebreider analyseren en playbooks maken voor een effectieve en onmiddellijke reactie.

### <a name="azure-information-protection"></a>Azure Information Protection
Onlangs hebben we de integratie van Azure Information Protection afgeschaft, omdat onze endpoint-DLP-mogelijkheden een verbeterde detectie- en beveiligingsoplossing bevatten voor gevoelige gegevens die zijn opgeslagen op eindpuntapparaten, zodat er meer zichtbaarheid en integratie tussen oplossingen mogelijk is. Dit is aangekondigd in de volgende [blog.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555) We raden klanten aan over te gaan op het gebruik van Endpoint DLP.

### <a name="conditional-access"></a>Voorwaardelijke toegang
De dynamische apparaatrisicoscore van Microsoft Defender voor Eindpunt is geïntegreerd in de evaluatie Voorwaardelijke toegang, zodat alleen veilige apparaten toegang hebben tot resources. 

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security gebruikt Microsoft Defender voor eindpuntsignalen om direct inzicht te krijgen in het gebruik van cloudtoepassing, waaronder het gebruik van niet-ondersteunde cloudservices (schaduw-IT) van alle bewaakte apparaten van Microsoft Defender voor Endpoint.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity
Verdachte activiteiten zijn processen die worden uitgevoerd onder een gebruikerscontext. De integratie tussen Microsoft Defender voor Eindpunt en Microsoft Defender voor identiteit biedt de flexibiliteit om een cyberbeveiligingsonderzoek uit te voeren tussen activiteiten en identiteiten.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender voor Office
[Defender voor Office 365](/office365/securitycompliance/office-365-atp) helpt uw organisatie te beschermen tegen malware in e-mailberichten of bestanden via Safe Koppelingen, Safe Bijlagen, geavanceerde mogelijkheden voor anti-phishing en spoof intelligence. De integratie tussen Microsoft Defender voor Office 365 en Microsoft Defender voor Eindpunt stelt beveiligingsanalisten in staat om upstream te gaan om het ingangspunt van een aanval te onderzoeken. Door het delen van bedreigingsinformatie kunnen aanvallen worden beperkt en geblokkeerd. 

>[!NOTE]
> Defender voor Office 365 gegevens wordt weergegeven voor gebeurtenissen in de afgelopen 30 dagen. Voor waarschuwingen worden Defender voor Office 365 weergegeven op basis van de eerste activiteitstijd. Daarna zijn de gegevens niet meer beschikbaar in Defender voor Office 365.

### <a name="skype-for-business"></a>Skype voor Bedrijven
De Skype voor Bedrijven biedt analisten een manier om te communiceren met een mogelijk gecompromitteerde gebruiker of apparaateigenaar via een eenvoudige knop vanuit de portal.

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender
Met Microsoft 365 Defender, Microsoft Defender voor Eindpunt en diverse microsoft-beveiligingsoplossingen vormen ze een geïntegreerde suite voor bedrijfsdefensie vóór en na inbreuk die inheems is geïntegreerd in eindpunten, identiteit, e-mail en toepassingen om geavanceerde aanvallen te detecteren, te voorkomen, te onderzoeken en automatisch te beantwoorden. 
 
[Meer informatie over Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)


## <a name="related-topics"></a>Verwante onderwerpen
- [Integratie en andere geavanceerde functies configureren](advanced-features.md)
- [Microsoft 365 Overzicht van Defender](/microsoft-365/security/defender/microsoft-threat-protection)
- [Microsoft 365 Defender inschakelen](/microsoft-365/security/defender/mtp-enable)
- [Gebruikers, gegevens en apparaten beveiligen met Voorwaardelijke toegang](conditional-access.md)
