---
title: Veelgestelde vragen over Office 365 Video networking
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
description: Hier vindt u antwoorden op de meestgestelde vragen over bandbreedteplanning, versleuteling en & hoe de service gebruik maakt van cdn's (Content Delivery Networks).
ms.openlocfilehash: 8bc0a69ff744967d24aa7d21ed6daee1a839f159
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921568"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Veelgestelde vragen over Office 365 Video networking

Met de Office 365 Video-opslagplaats en streamingservices kunt u eenvoudig video's opslaan en streamen binnen uw organisatie. Er is veel informatie over [Office 365 Video;](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50) Deze veelgestelde vragen over netwerken zijn bedoeld om de meest voorkomende vragen over bandbreedteplanning, versleuteling en de manier waarop de service gebruik maakt van CDN's [(Content Delivery Networks)](content-delivery-networks.md) te beantwoorden.
  
Als u nog niet goed weet wat er gebeurt wanneer een video wordt geüpload of afgespeeld, bekijkt u deze video die we samen hebben gemaakt: Wat gebeurt er met een videobestand wanneer deze wordt geüpload naar [Office 365 Video.](https://www.youtube.com/watch?v=HXSZ0jYBKlM)
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Wat zijn de bandbreedtevereisten voor Office 365 Video?

Er zijn een groot aantal [ondersteunde video-indelingen](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) die kunnen worden geüpload naar Office 365. Elk videobestand wordt vervolgens gecodeerd naar een standaardindeling met verschillende videokwaliteiten voor afspelen. Office 365 Video gebruikt adaptieve bitratestreaming om de beste afspeelkwaliteit voor video te selecteren op basis van de beschikbare netwerkbandbreedte en de grootte van de videospeler. Hiervoor vraagt de speler in eerste instantie om de laagste afspeelkwaliteit. De service begint vervolgens met het verzenden van videosegmenten van 2 seconden naar de videospeler. De speler kan vervolgens een hogere of lagere afspeelkwaliteit aanvragen op basis van hoe snel elk segment wordt geleverd.
  
De adaptieve bitratestreaming doet dit alles op de achtergrond terwijl de video wordt afgespeeld met de minste mate van onderbreking of buffering. Tijdens het afspelen van video's kan de videospeler de automatische afspeelkwaliteit handmatig overschrijven om een specifieke afspeelkwaliteit voor video's te selecteren.
  
Hier is een snelle tabel met een overzicht van de netwerkvereisten voor elk van de afspeelkwaliteiten van de video. De minimale bandbreedte per persoon die nodig is om een video af te spelen, is 802 Kbps.
  
| Afspeelkwaliteit | Netwerksnelheid |
|:-----|:-----|
|288p  <br/> |802 Kbps  <br/> |
|360p  <br/> |1,2 Mbps  <br/> |
|576p  <br/> |2,5 Mbps  <br/> |
|720p  <br/> |3,8 Mbps  <br/> |

([Terug naar boven](office-365-video-networking-faq.md))
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>Hoe kunnen CDN's (Content Delivery Networks) het afspelen van video's helpen?

Als meerdere personen van dezelfde organisatie binnen dezelfde geografische locatie dezelfde video(s) streamen, worden in CDN's een kopie van deze video's opgeslagen op een locatie dichter bij die geografische regio. Als de video is opgeslagen of in de cache opgeslagen op de dichtstbijzijnde locatie, streamt elke persoon de video vanaf de locatie die het dichtst bij hem of haar staat in plaats van een locatie verderop. Office 365 Video gebruikt Azure Media Services om te beheren wat in de cache is opgeslagen in de Azure CDN's en voor hoelang. Azure Media Services kan een van de [Azure CDN-locaties gebruiken](/azure/cdn/cdn-pop-locations) om videofragmenten en manifesten een paar dagen in de cache te plaatsen. Als personen in uw organisatie de video's in de cache blijven bekijken, blijven ze in de cache. Als er meerdere dagen niemand toegang heeft tot de video, wordt de video uiteindelijk uit de cache verwijderd. De volgende keer dat iemand de video probeert te bekijken, wordt deze opnieuw in de cache opgeslagen op de dichtstbijzijnde CDN-locatie.
  
Iedereen die de video probeert te bekijken terwijl de inhoud in de cache wordt opgeslagen bij een nabijgelegen CDN, profiteert ervan dat de video dichterbij is en in de meeste gevallen minder hops verwijderd is. Hierdoor wordt de afspeelsnelheid van video verbeterd. De netwerkvereisten voor het afspelen van de video worden echter niet gewijzigd.
  
> [!NOTE]
> Er zijn enkele omstandigheden, zoals het bereiken van de capaciteitslimiet, waarbij de video mogelijk wordt verwijderd voordat de drie dagen zijn bereikt.
  
([Terug naar boven](office-365-video-networking-faq.md))
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>Kan ik de video's lokaal cachen voor een snellere weergave?

Ja. Office 365 verhindert niet dat u een lokaal CDN of een caching-proxy gebruikt om video of andere Office 365-inhoud naar uw lokale netwerk te brengen voor snellere toegang. Er zijn verschillende manieren om een lokale caching-oplossing in uw netwerk te implementeren, de meest voorkomende methode is om een proxyoplossing te gebruiken waarmee inhoud lokaal wordt gecachet. Wanneer een proxy of privé-CDN de videofragmenten en -manifesten in de cache heeft opgeslagen, worden toekomstige aanvragen voor bestanden die via de proxy of privé-CDN worden gerouteerd, uit de lokale cache gehaald en niet van een internetlocatie gehaald. Houd rekening met de gelijktijdigheid van netwerkbandbreedte, capaciteit en videoweergave tijdens de planning van een oplossing als deze.
  
([Terug naar boven](office-365-video-networking-faq.md))
  
## <a name="how-videos-are-encrypted-and-secured"></a>Hoe worden video's versleuteld en beveiligd?

Office 365 Video weet hoe belangrijk het is om uw gegevens veilig en privé te houden. [Microsoft Trust Center beschrijft](https://products.office.com/business/office-365-trust-center-welcome) onze betrokkenheid bij de privacy en beveiliging van uw inhoud. Bij het afspelen van video is snelheid belangrijk voor een goede ervaring. We brengen echter uw beveiliging of privacy niet in gevaar in ruil voor snelheid. Hier wordt tegemoet gekomen aan snelheid, beveiliging en privacy.
  
Wanneer u of iemand in uw organisatie een nieuwe video uploadt, wordt deze video getranscodeerd, versleuteld met AES-128-versleuteling en opgeslagen in Azure Media Services. Dit betekent dat de video's zowel onderweg als in rust zijn versleuteld.
  
Wanneer iemand in uw organisatie een nieuwe video probeert te bekijken, volgt deze de volgende stappen:
  
1. Vraag SharePoint Online of ze toestemming hebben om de video te bekijken.

2. SharePoint Online gebruikt de bestandsmachtigingen om te bepalen of de persoon de video kan bekijken.

3. Als dit is toegestaan, wordt in SharePoint Online een token opgehaald uit Azure om aan de videospeler te geven.

4. De videospeler gebruikt vervolgens het token om de ontsleutelingssleutel op te vragen bij Azure.

5. Met de ontsleutelingssleutel in de hand kan de videospeler de video streamen.

![O365 Video afspelen](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([Terug naar boven](office-365-video-networking-faq.md))
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>Wat zijn de vereisten voor het afspelen van Office 365 Video?

Ondersteunde besturingssystemen en webbrowsers van Office 365 Video zijn hetzelfde als de Vereisten voor SharePoint Online in [office 365-systeemvereisten.](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45) Afhankelijk van welk besturingssysteem en welke webbrowserconfiguratie u hebt, bepaalt u de specifieke behoeften van de videospeler. Hier vindt u meer informatie over vereisten voor [het afspelen van video' s.](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
([Terug naar boven](office-365-video-networking-faq.md))
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>Ik kan Office 365-video niet laten werken, waar moet ik beginnen?

Bij het oplossen van problemen met de verbinding met Office 365 Video zijn problemen met uw netwerk, uw internetproviders en uw configuratie van Office 365 vereist. De eerste plaats om te beginnen is het dashboard voor service-status. Hier ziet u dat er al dan niet een probleem is met Office 365 Video. Als alles er goed uitziet, vindt u hier enkele extra informatiebronnen om u te helpen.
  
- Zorg ervoor dat u verbinding kunt maken met de [netwerk-eindpunten die vereist zijn voor Office 365 Video.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- Controleer uw netwerkconnectiviteit met behulp van onze handleiding voor het oplossen van problemen met [office 365-netwerken.](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- Bekijk onze [best practices voor het gebruik van Office 365 op een traag netwerk.](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)

- [Help bij het configureren van Office 365 Video.](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)

([Terug naar boven](office-365-video-networking-faq.md))
  
## <a name="office-365-video-resources"></a>Office 365 Video-resources

Hier vindt u enkele andere bronnen om u te helpen Office 365 Video te implementeren en te gebruiken:
  
[Help-informatie over de configuratie van Office 365 Video zoeken](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Kennismaken met Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[Een kanaal maken en beheren in Office 365 Video](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Uw Office 365 Video-portal beheren](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[Video-indelingen die werken in Office 365 Video](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([Terug naar boven](office-365-video-networking-faq.md))
  
Met deze korte koppeling kunt u teruggaan: [https://aka.ms/video365networkfaq]()