---
title: Microsoft Threat Protection
description: Microsoft Threat Protection is een gecoördineerde oplossing voor bedreigingsbescherming die is ontworpen om apparaten, identiteit, gegevens en toepassingen te beschermen
keywords: introductie tot Microsoft Threat Protection, cyber security, geavanceerde permanente bedreiging, enterprise security, apparaten, apparaat, identiteit, gebruikers, gegevens, applicaties, incidenten, geautomatiseerd onderzoek en herstel, geavanceerde jacht
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
ms.openlocfilehash: 0e51e52db4e569716954aada1c5cea35ddc6dd0a
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528367"
---
# <a name="microsoft-threat-protection"></a>Microsoft Threat Protection

**Geldt voor:**
- Microsoft Threat Protection



Microsoft Threat Protection is een uniforme verdedigingssuite voor en na de inbreuk op ondernemingen die detectie, preventie, onderzoek en respons op endpoints, identiteiten, e-mail en toepassingen native coördineert om geïntegreerde bescherming te bieden tegen geavanceerde aanvallen.

Met de geïntegreerde Microsoft Threat Protection-oplossing kunnen beveiligingsprofessionals de bedreigingssignalen die elk van deze producten ontvangen samenvoegen en de volledige omvang en impact van de bedreiging bepalen; hoe het in de omgeving is gekomen, wat het wordt beïnvloed en hoe het momenteel van invloed is op de organisatie. Microsoft Threat Protection onderneemt automatische actie om de aanval te voorkomen of te stoppen en aangetaste postvakken, eindpunten en gebruikersidentiteiten zelf te genezen.  


<center><h2>Microsoft Threat Protection-services</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Geavanceerde bescherming voor geavanceerde bedreigingen van Microsoft Defender</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Geavanceerde bedreigingsbeveiliging van Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Azure Advanced Threat Protection</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Beveiliging van Microsoft Cloud-apps</b></a></center></td>
</tr>
</table>
<br>



Microsoft Threat Protection-suite beschermt: 
- **Eindpunten met Microsoft Defender ATP** - Microsoft Defender ATP is een uniform eindpuntplatform voor preventieve bescherming, detectie na inbreuk, geautomatiseerd onderzoek en respons. 
- **E-mail en samenwerking met Office 365 ATP** - Office 365 ATP beschermt uw organisatie tegen schadelijke bedreigingen die worden veroorzaakt door e-mailberichten, koppelingen (URL's) en samenwerkingstools. 
- **Identiteiten met Azure ATP en Azure AD Identity Protection** - Azure ATP gebruikt Active Directory-signalen om geavanceerde bedreigingen, gecompromitteerde identiteiten en schadelijke insideracties gericht op uw organisatie te identificeren, detecteren en onderzoeken. 
- **Toepassingen met Microsoft Cloud App-beveiliging** - Microsoft Cloud App-beveiliging is een uitgebreide cross-SaaS-oplossing die diepe zichtbaarheid, sterke gegevensbesturingselementen en verbeterde bescherming van bedreigingen voor uw cloud-apps biedt. 

De unieke cross-productlaag van Microsoft Threat Protection breidt de afzonderlijke suitecomponenten uit tot:
- Bescherm tegen aanvallen en coördineer defensieve reacties in de suite door middel van signaaldeling en geautomatiseerde acties
- Vertel het volledige verhaal van de aanval over productwaarschuwingen, gedrag ingen en context voor beveiligingsteams door gegevens over waarschuwingen, verdachte gebeurtenissen en beïnvloede assets aan te sluiten bij 'incidenten'
- Automatiseer de reactie op compromissen door zelfgenezing voor beïnvloede assets te activeren door middel van geautomatiseerde herstel
- Beveiligingsteams in staat stellen gedetailleerde en effectieve bedreigingen jacht uit te voeren op alle eindpunt- en Office-gegevens

![Afbeelding van overzichtspagina voor incidenten](../../media/overview-incident.png) <br>
Cross-product incident (Overzicht)

![Afbeelding van de wachtrij voor waarschuwingen](../../media/incident-list.png)<br>
Alle gerelateerde waarschuwingen in de suiteproducten correleerden samen in één incident (waarschuwingsweergave)

![Afbeelding van de incidentenwachtrij](../../media/advanced-hunting.png)<br>
Op query's gebaseerde jacht bovenop e-mail- en eindpuntgegevens


Functies voor cross-product van Microsoft Threat Protection omvatten: 
- **Cross-product enkele ruit -** Centraal bekijk alle informatie voor detecties, beïnvloedactiva, geautomatiseerde acties uitgevoerd, en aanverwante bewijzen in een enkele wachtrij en een enkel venster in [security.microsoft.com](https://security.microsoft.com). 
- **Gecombineerde wachtrij voor incidenten** - Om beveiligingsprofessionals te helpen zich te concentreren op wat van cruciaal belang is door ervoor te zorgen dat de volledige aanvalsscope wordt beheerd, worden beïnvloede assets en geautomatiseerde herstelacties gegroepeerd en tijdig opgedoken. 
- **Automatische reactie op bedreigingen** - Kritieke bedreigingsinformatie wordt in realtime gedeeld tussen de Microsoft Threat Protection-producten om de voortgang van een aanval te stoppen. Als er bijvoorbeeld een kwaadaardig bestand wordt gedetecteerd op een eindpunt dat wordt beschermd door Microsoft Defender ATP, wordt Office 365 ATP geïnstrueerd om het bestand uit alle e-mailberichten te scannen en te verwijderen. Het bestand wordt ter plekke geblokkeerd door de volledige Microsoft 365-beveiligingssuite.
- **Zelfherstellend voor gecompromitteerde apparaten, gebruikersidentiteiten en postvakken** - Microsoft Threat Protection maakt gebruik van automatische acties en playbooks die door AI worden aangedreven om de getroffen assets terug te sturen naar een veilige staat. Microsoft Threat Protection maakt gebruik van automatische herstelmogelijkheden van de suiteproducten om ervoor te zorgen dat alle getroffen assets die verband houden met een incident, waar mogelijk automatisch worden verholpen.
- **Cross-product threat hunting** - Security teams kunnen gebruik maken van hun unieke organisatorische kennis om te jagen voor tekenen van compromis door het creëren van hun eigen aangepaste query's over de ruwe gegevens verzameld door de verschillende beschermingsproducten. Microsoft Threat Protection biedt op query's gebaseerde toegang tot 30 dagen historische ruwe signalen en waarschuwingsgegevens over eindpunt- en Office 365 ATP-gegevens. 


## <a name="get-started"></a>Aan de slag
Aan de licentievereisten voor Microsoft Threat Protection moet worden voldaan voordat u de service inschakelen in het Microsoft 365-beveiligingscentrum op [security.microsoft.com.](https://security.microsoft.com) Voor meer informatie, lees:
- [Licentievereisten](prerequisites.md#licensing-requirements)
- [Microsoft Threat Protection inschakelen](mtp-enable.md)
