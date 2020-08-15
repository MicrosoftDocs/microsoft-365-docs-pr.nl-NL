---
title: Veelgestelde vragen over Office 365 video-netwerken
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: Hier vindt u antwoorden op de meest gestelde vragen over de bandbreedte, de versleuteling, & de manier waarop de service Content Delivery Networks (Cdn's) gebruikt.
ms.openlocfilehash: e08a67988290e7ead87ff30a5ebdf9c8560f4825
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695678"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Veelgestelde vragen over Office 365 video-netwerken

Met de Office 365-Video's bibliotheek en streaming kunt u eenvoudig Video's in uw organisatie opslaan en streaming. De [video van Office 365](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)biedt veel fantastische informatie. met veelgestelde vragen over het netwerk kunt u de meest voorkomende vragen over de bandbreedte, de versleuteling en de werking van de service voor [Content levering](content-delivery-networks.md) (cdn's) beantwoorden.
  
Als u nog niet eerder begrijpt wat er gebeurt als een video wordt geüpload of weer gespeeld, hebt u een kijkje in deze video, [Wat gebeurt er met een videobestand wanneer ze worden geüpload naar Office 365 video](https://www.youtube.com/watch?v=HXSZ0jYBKlM).
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Wat zijn de vereisten voor Office 365 video-bandbreedte?

Er zijn diverse [ondersteunde video-indelingen](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) die kunnen worden geüpload naar Office 365. Elk videobestand wordt vervolgens gecodeerd met een standaardindeling met verschillende video kwaliteiten, zodat ze kunnen worden afgespeeld. In Office 365 video wordt gebruikgemaakt van adaptieve bitsnelheid om de beste kwaliteit voor afspelen van video te selecteren op basis van de beschikbare netwerkbandbreedte en-grootte van de video speler. Hiervoor vraagt de speler eerst de laagste afspeelkwaliteit. De service begint vervolgens met het verzenden van 2-Second video segmenten naar de videospeler. De speler kan vervolgens een hogere of lagere afspeelkwaliteit aanvragen op basis van hoe snel elk segment wordt afgeleverd.
  
De verhoudingen van streaming bitsnelheid doet alles op de achtergrond, terwijl de video wordt afgespeeld met het kleinste aantal storingen of buffering. Tijdens het afspelen van een video kunt u met de viewer van de videospeler de automatische kwaliteit van de video handmatig wijzigen, zodat u een specifieke kwaliteit voor het afspelen van een video kunt selecteren.
  
Hier ziet u een snelle tabel waarin de netwerkvereisten voor elk van de beeldscherm kwaliteiten worden beschreven. De minimale bandbreedte per persoon die nodig is om een video af te spelen is 802Kbps.
  
| Afspeelkwaliteit | Netwerksnelheid |
|:-----|:-----|
|288p  <br/> |802Kbps  <br/> |
|360p  <br/> |1,2 Mbps  <br/> |
|576p  <br/> |2,5 Mbps  <br/> |
|720p  <br/> |3,8 Mbps  <br/> |

([Terug naar boven](office-365-video-networking-faq.md))
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>Hoe zorgen netwerken voor content levering (Cdn's) bij het afspelen van Video's?

Als er meerdere personen in dezelfde geografische locatie in dezelfde geografische locatie worden gestreamd, wordt een kopie van deze Video's opgeslagen op een locatie die dichter bij die geografische regio valt. Wanneer de video is opgeslagen of op de dichtstbijzijnde locatie is opgeslagen, streamt elke persoon de video vanaf de locatie die het dichtst bij u is, in plaats van ergens verder. In Office 365 video worden Azure Media Services gebruikt voor het beheren van wat in de cache van de Azure Cdn's en voor hoelang. Azure Media Services kan gebruikmaken van een van de [Azure CDN-locaties](https://azure.microsoft.com/documentation/articles/cdn-pop-locations/) om gedurende een paar dagen videofragmenten en manifesten op te cacheen. Als de personen in uw organisatie de in de cache geplaatste Video's blijven bekijken, blijven ze in de cache aanwezig. Als niemand de video gedurende enkele dagen opent, wordt de video uiteindelijk neergezet van de cache. De volgende keer dat iemand probeert de video te bekijken, wordt deze opnieuw in de cache opgeslagen op de dichtstbijzijnde CDN-locatie.
  
Iedereen die de video probeert te bekijken terwijl de inhoud in de cache wordt opgeslagen in een nabije CDN voordelen van de video, en in de meeste gevallen met minder hops. Dit verbetert de afspeelsnelheid van een video. het is echter niet van invloed op de netwerkvereisten om de video af te spelen.
  
> [!NOTE]
> Er gelden enkele omstandigheden, zoals de capaciteitslimiet die wordt bereikt, waarbij de video kan worden verwijderd voordat de drie dagen zijn bereikt.
  
([Terug naar boven](office-365-video-networking-faq.md))
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>Kan ik de Video's in een lokale cache opslaan voor een betere afspeelsnelheid?

Ja. In Office 365 kunt u geen lokale CDN of een proxy voor cache gebruiken om video-of andere inhoud van Office 365 naar uw lokale netwerk te brengen zodat u deze sneller kunt gebruiken. U kunt op verschillende manieren een lokale oplossing voor het opslaan van de cache implementeren in uw netwerk, de meest voorkomende methode is het gebruik van een proxy oplossing die inhoud lokaal in cache opslaat. Wanneer een proxy of private CDN de videofragmenten en manifesties in de cache heeft geplaatst, worden toekomstige aanvragen voor de bestanden die door de proxy of de persoonlijke CDN worden verstuurd, opgehaald uit de lokale cache en niet opgehaald van een internetlocatie. Houd rekening met de bandbreedte van het netwerk, de capaciteit en het afspelen van video tijdens het plannen van een oplossing zoals deze.
  
([Terug naar boven](office-365-video-networking-faq.md))
  
## <a name="how-videos-are-encrypted-and-secured"></a>Hoe worden Video's versleuteld en beveiligd?

Met Office 365 video weet u wat belangrijk is om uw gegevens veilig en privé te houden. In het [Microsoft Vertrouwenscentrum](https://products.office.com/business/office-365-trust-center-welcome) wordt de privacy en beveiliging van uw inhoud beschreven. Met het afspelen van video is de snelheid belangrijk voor een goede ervaring; uw veiligheid en privacy in Exchange worden echter niet aangetast. Hier ziet u hoe we de snelheid, beveiliging en privacy voor ons willen bieden.
  
Wanneer u of iemand in uw organisatie een nieuwe video laadt, wordt die video versleuteld en versleuteld met AES-128-versleuteling en opgeslagen in azure Media Services. Dit betekent dat de Video's beide worden versleuteld in transit en de rest.
  
Wanneer iemand in uw organisatie een nieuwe video wil bekijken, volgen ze deze stappen:
  
1. Vraag SharePoint Online of ze gemachtigd zijn om de video te bekijken.

2. In SharePoint Online wordt aan de hand van de bestandsmachtigingen bepaald of de persoon de video mag bekijken.

3. Als ze zijn toegestaan, haalt SharePoint Online een token op uit Azure en geeft deze door aan de videospeler.

4. De videospeler gebruikt vervolgens de token om de ontsleutelingssleutel bij Azure op te vragen.

5. Met de ontsleutelingssleutel is de videospeler in staat om de video te streamen.

![Afspelen van een O365-video](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([Terug naar boven](office-365-video-networking-faq.md))
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>Wat zijn de vereisten voor het afspelen van Office 365-video?

Ondersteunde besturingssystemen en webbrowsers van Office 365 zijn dezelfde als de vereisten voor SharePoint Online in de [systeemvereisten voor office 365](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45). Afhankelijk van het besturingssysteem en de configuraties van een webbrowser, bepaalt u de specifieke behoeften van de videospeler. Hier vindt u meer informatie over de vereisten voor het [afspelen van Video's](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6).
  
([Terug naar boven](office-365-video-networking-faq.md))
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>Ik kan de video van Office 365 niet aan de slag

Verbindingsproblemen met Office 365-video oplossen maakt het probleem met uw netwerk, uw INTERNETPROVIDER (s) en de configuratie van Office 365. De eerste keer dat u begint, is het dashboard voor de servicestatus. U krijgt dan iets aan de video van Office 365. Als alles er geweldig uitziet, kunt u hier meer informatiebronnen vinden om u te helpen.
  
- Controleer of u verbinding kunt maken met de [netwerkeindpunten die vereist zijn voor Office 365 video](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

- Controleer uw netwerkverbinding met de [gids voor probleemoplossing van Office 365](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).

- Zie onze [Aanbevolen procedures voor het gebruik van Office 365 op een traag netwerk](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166).

- [Help-informatie over de configuratie van Office 365-video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50).

([Terug naar boven](office-365-video-networking-faq.md))
  
## <a name="office-365-video-resources"></a>Video bronnen voor Office 365

Hier volgen enkele andere informatiebronnen die u kunt gebruiken om Office 365-video te implementeren en te gebruiken:
  
[Help-informatie zoeken over de configuratie van Office 365 video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Kennismaken met Office 365 video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[Een kanaal maken en beheren in Office 365 video](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Uw Office 365 video-portal beheren](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[Video-indelingen die kunnen worden gebruikt in Office 365-video](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([Terug naar boven](office-365-video-networking-faq.md))
  
Met deze korte koppeling kunt u teruggaan: [https://aka.ms/video365networkfaq](https://aka.ms/video365networkfaq)
