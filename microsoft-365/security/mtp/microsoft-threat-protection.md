---
title: Microsoft Threat Protection
description: Microsoft Threat Protection is een gecoördineerde oplossing voor bedreigingsbescherming die is ontworpen om apparaten, identiteit, gegevens en toepassingen te beschermen
keywords: introductie tot Microsoft Threat Protection, cyber security, geavanceerde persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: afeef8de09e0ee7a727372041791871712ca4e0d
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560893"
---
# <a name="microsoft-threat-protection"></a>Microsoft Threat Protection

**Van toepassing op:**
- Microsoft Threat Protection



Microsoft Threat Protection is een uniforme pre- en post-breach enterprise defense suite die detectie, preventie, onderzoek en respons op basis van eindpunten, identiteiten, e-mail en toepassingen native coördineert om geïntegreerde bescherming te bieden tegen geavanceerde aanvallen.

Met de geïntegreerde Microsoft Threat Protection-oplossing kunnen beveiligingsprofessionals de dreigingssignalen aan elkaar naaien die elk van deze producten ontvangt en de volledige reikwijdte en impact van de dreiging bepalen; hoe het in de omgeving is terechtgekomen, wat het heeft beïnvloed en hoe het momenteel van invloed is op de organisatie. Microsoft Threat Protection neemt automatisch actie om de aanval te voorkomen of te stoppen en de getroffen mailboxen, eindpunten en gebruikersidentiteiten zelf te genezen.  


<center><h2>Microsoft Threat Protection-services</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender Geavanceerde bedreigingsbescherming</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Geavanceerde bedreigingsbeveiliging van Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Azure Advanced Threat Protection</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Beveiliging van Microsoft Cloud-app</b></a></center></td>
</tr>
</table>
<br>


>[!TIP]
>Bekijk deze [interactieve handleiding voor Microsoft Threat Protection.](https://aka.ms/MTP-Interactive-Guide)


Microsoft Threat Protection suite beschermt: 
- **Eindpunten met Microsoft Defender ATP** - Microsoft Defender ATP is een uniform endpoint-platform voor preventieve bescherming, detectie na inbreuk, geautomatiseerd onderzoek en respons. 
- **E-mail en samenwerking met Office 365 ATP** - Office 365 ATP beschermt uw organisatie tegen schadelijke bedreigingen van e-mailberichten, koppelingen (URL's) en samenwerkingshulpprogramma's. 
- **Identiteiten met Azure ATP en Azure AD Identity Protection** - Azure ATP gebruikt Active Directory-signalen om geavanceerde bedreigingen, gecompromitteerde identiteiten en schadelijke insideracties gericht op uw organisatie te identificeren, te detecteren en te onderzoeken. 
- **Toepassingen met Microsoft Cloud App-beveiliging** - Microsoft Cloud App-beveiliging is een uitgebreide cross-SaaS-oplossing die uw cloud-apps diepgaand inzicht, sterke gegevenscontroles en verbeterde bedreigingsbescherming biedt. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

De unieke cross-productlaag van Microsoft Threat Protection vergroot de afzonderlijke suitecomponenten tot:
- Help beschermen tegen aanvallen en coördineer defensieve reacties in de suite door middel van signaaldeling en geautomatiseerde acties
- Vertel het volledige verhaal van de aanval over productwaarschuwingen, gedrag en context voor beveiligingsteams door gegevens over waarschuwingen, verdachte gebeurtenissen en beïnvloede assets te verbinden aan 'incidenten'
- Automatiseer de respons op compromissen door zelfherstellende voor beïnvloede assets te activeren door middel van geautomatiseerde sanering
- Beveiligingsteams in staat stellen gedetailleerde en effectieve bedreigingsjacht uit te voeren via endpoint- en Office-gegevens

![Afbeelding van de pagina incidentoverzicht](../../media/overview-incident.png) <br>
Incident met verschillende producten (overzicht)

![Afbeelding van waarschuwingswachtrij](../../media/incident-list.png)<br>
Alle gerelateerde waarschuwingen voor de suiteproducten die samengekoppeld zijn in één incident (waarschuwingenweergave)

![Afbeelding van de wachtrij voor incidenten](../../media/advanced-hunting.png)<br>
Op query gebaseerde jacht bovenop e-mail- en eindpuntreintegegevens


Microsoft Threat Protection-functies voor verschillende producten zijn onder andere: 
- **Cross-product enkel glas -** Centrale weergave van alle informatie voor detecties, beïnvloede activa, geautomatiseerde acties en bijbehorend bewijsmateriaal in één wachtrij en één ruit in [security.microsoft.com](https://security.microsoft.com). 
- **Gecombineerde incidentenwachtrij** - Om beveiligingsprofessionals te helpen zich te concentreren op wat essentieel is door ervoor te zorgen dat de volledige aanvalsbereik, beïnvloede assets en geautomatiseerde herstelacties tijdig worden gegroepeerd en opgedoken. 
- **Automatische reactie op bedreigingen** - Kritieke dreigingsinformatie wordt in realtime gedeeld tussen de Microsoft Threat Protection-producten om de voortgang van een aanval te stoppen. Als een kwaadaardig bestand bijvoorbeeld wordt gedetecteerd op een eindpunt dat is beveiligd door Microsoft Defender ATP, wordt Office 365 ATP geïnstrueerd om het bestand uit alle e-mailberichten te scannen en te verwijderen. Het bestand wordt geblokkeerd op zicht door de gehele Microsoft 365-beveiligingssuite.
- **Zelfgenezing voor gecompromitteerde apparaten, gebruikersidentiteiten en postvakken** - Microsoft Threat Protection maakt gebruik van automatische acties en playbooks met AI om beïnvloede assets terug te brengen naar een veilige status. Microsoft Threat Protection maakt gebruik van automatische herstelmogelijkheden van de suiteproducten om ervoor te zorgen dat alle getroffen assets die verband houden met een incident waar mogelijk automatisch worden gesaneerd.
- **Cross-product threat hunting** - Security teams kunnen gebruik maken van hun unieke organisatorische kennis om te jagen voor tekenen van compromis door het creëren van hun eigen aangepaste vragen over de ruwe gegevens verzameld door de verschillende beschermingsproducten. Microsoft Threat Protection biedt toegang op query's tot 30 dagen historische onbewerkte signalen en waarschuwingsgegevens voor endpoint- en Office 365 ATP-gegevens. 


## <a name="get-started"></a>Aan de slag
Microsoft Threat Protection-licentievereisten moeten worden vervuld voordat u de service inschakelen in het Microsoft 365-beveiligingscentrum op [security.microsoft.com](https://security.microsoft.com). Voor meer informatie, lees:
- [Vergunningsvereisten](prerequisites.md#licensing-requirements)
- [Microsoft Threat Protection inschakelen](mtp-enable.md)
