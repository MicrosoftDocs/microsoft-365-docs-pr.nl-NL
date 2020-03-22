---
title: Wat is het verschil tussen ongewenste e-mail en bulke-mail?
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/7/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: Klanten vragen soms wat is het verschil tussen ongewenste e-mail en bulk e-mailberichten? Het doel van dit onderwerp is om het verschil uit te leggen en om informatie te verstrekken over de verschillende opties die beschikbaar zijn voor zowel In Exchange Online en Exchange Online Protection (EOP).
ms.openlocfilehash: 55924ac5e83ca109fd66d1723cdb7c5f43f20df6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895033"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>Wat is het verschil tussen ongewenste e-mail en bulke-mail?

Klanten vragen soms "wat is het verschil tussen ongewenste e-mail en bulk e-mailberichten?" Het doel van dit onderwerp is om het verschil uit te leggen en om informatie te verstrekken over de verschillende opties die beschikbaar zijn voor zowel In Exchange Online en Exchange Online Protection (EOP).
  
 **Wat is ongewenste e-mail?**
  
Ongewenste e-mailberichten zijn "spam"-berichten, die ongevraagde (en meestal ongewenste) e-mailberichten zijn die door de service worden gefilterd. Standaard wijst de service het spambericht af op basis van de reputatie van het verzendende IP-adres. Als het echter door de IP-inspectie wordt doorgegeven, maar door de inhoudsfilters als spam wordt geclassificeerd, wordt het bericht verzonden naar de map Ongewenste e-mail van de beoogde ontvangers. 
  
> [!NOTE]
> De actie die wordt uitgevoerd op door inhoud gefilterde berichten, kan worden geconfigureerd via inhoudsfilterbeleid in het Exchange-beheercentrum (EAC), zoals beschreven in [Beleid voor antispam configureren in Office 365](configure-your-spam-filter-policies.md). Ook als u het niet eens bent met de spamclassificatie, u berichten die u als spam of niet-spam beschouwt op verschillende manieren aan Microsoft rapporteren, zoals beschreven in [Spam verzenden, niet-spam en phishing-scamberichten aan Microsoft voor analyse.](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md) 
  
 **Wat is bulk e-mail?**
  
Bulk e-mail, ook wel grijze e-mail genoemd, is een type e-mailbericht dat moeilijker te classificeren is. Terwijl ongewenste e-mail is een constante bedreiging, bulk e-mail is meestal samengesteld uit een advertentie of marketing bericht dat is waarschijnlijk niet herhaaldelijk verzonden. Bulk e-mail wordt gezocht door sommige gebruikers, en in feite kunnen ze opzettelijk hebben aangemeld om deze berichten te ontvangen, terwijl andere gebruikers kunnen overwegen dit soort berichten te zijn spam. Sommige gebruikers willen bijvoorbeeld advertentie-e-mails van de Contoso Corporation of uitnodigingen voor een komende conferentie over cyberbeveiliging ontvangen, terwijl andere gebruikers dergelijke e-mails als spam beschouwen.
  
## <a name="how-to-manage-bulk-email"></a>Bulke-mail beheren

Hoe bulk e-mail te beheren is niet een duidelijke cut beslissing, want als alle bulk e-mail is geclassificeerd als spam, de gebruikers die het willen kan klagen en indienen als een vals-positief (niet-spam) bericht dat ten onrechte werd gemarkeerd als spam. Aan de andere kant, als alle bulk e-mail wordt verhuurd door, de gebruikers die niet willen dat het kan klagen en indienen als een gemiste spam-bericht (vals negatief) dat ten onrechte aangekomen in hun inbox.
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>Gevoeligheidscontrole voor bulkmail inschakelen in het inhoudsfilterbeleid

Afhankelijk van het beleid van uw bedrijf ten aanzien van bulke-mailberichten, kunnen beheerders een drempelwaarde selecteren om de bulke-mail toe te wijzen. De instelling is configureerbaar via inhoudsfilterbeleid in de EAC. Bekijk [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor de stappen. U een drempelinstelling kiezen van 1-9, waarbij 1 de meeste bulke-mail markeert als spam en 9 de meeste bulke-mail kan worden bezorgd. De service voert vervolgens de geconfigureerde actie uit, zoals het verzenden van het bericht naar de map Ongewenste e-mail van de ontvanger. 
  

