---
title: Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing
description: Gebruik de onderzoeksopties om mogelijke communicatie tussen apparaten en externe IP-adressen te onderzoeken.
keywords: onderzoeken, IP-adres, waarschuwing, microsoft defender atp, extern IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: ca7f5e9126ffd57f7e858210e006bc05459d567b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057565"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Bekijk mogelijke communicatie tussen uw apparaten en IP-adressen (External Internet Protocol).

Het identificeren van alle apparaten in de organisatie die hebben gecommuniceerd met een verdacht of bekend schadelijk IP-adres, zoals C2-servers (Command and Control), helpt bij het bepalen van het mogelijke bereik van inbreuk, bijbehorende bestanden en geïnfecteerde apparaten.

U vindt informatie uit de volgende secties in de IP-adresweergave:

- IP wereldwijd
- DNS-namen omkeren
- Waarschuwingen met betrekking tot dit IP-adres
- IP in organisatie
- Prevalentie

## <a name="ip-worldwide-and-reverse-dns-names"></a>IP Worldwide en Reverse DNS-namen

De sectie IP-adresgegevens bevat kenmerken van het IP-adres, zoals het ASN en de reverse DNS-namen.

## <a name="alerts-related-to-this-ip"></a>Waarschuwingen met betrekking tot dit IP-adres

De **sectie Waarschuwingen met betrekking tot deze IP-sectie** bevat een lijst met waarschuwingen die aan het IP-adres zijn gekoppeld.

## <a name="ip-in-organization"></a>IP in organisatie

De **sectie IP in organisatie** bevat details over de prevalentie van het IP-adres in de organisatie.

## <a name="prevalence"></a>Prevalentie

In **de sectie Prevalentie** wordt weergegeven hoeveel apparaten zijn verbonden met dit IP-adres en wanneer het IP-adres voor het eerst en voor het laatst is gezien. U kunt de resultaten van deze sectie filteren op tijdsperiode. de standaardperiode is 30 dagen.

## <a name="most-recent-observed-devices-with-ip"></a>Meest recente waargenomen apparaten met IP

De **sectie Meest recente waargenomen apparaten** met IP-adres biedt een chronologische weergave van de gebeurtenissen en bijbehorende waarschuwingen die zijn waargenomen op het IP-adres.

**Een extern IP-adres onderzoeken:**

1. Selecteer **IP** in **de** vervolgkeuzelijst Zoekbalk.
2. Voer het IP-adres in het **veld Zoeken** in.
3. Klik op het zoekpictogram of druk op **Enter.**

Details over het IP-adres worden weergegeven, waaronder: registratiedetails (indien beschikbaar), reverse-IP's (bijvoorbeeld domeinen), de aanwezigheid van apparaten in de organisatie die met dit IP-adres hebben gecommuniceerd (tijdens een selecteerbare periode) en de apparaten in de organisatie die met dit IP-adres zijn gecommuniceerd.

> [!NOTE]
> Zoekresultaten worden alleen geretourneerd voor IP-adressen die worden waargenomen in communicatie met apparaten in de organisatie.

Gebruik de zoekfilters om de zoekcriteria te definiëren. U kunt ook het zoekvak voor de tijdlijn gebruiken om de weergegeven resultaten te filteren van alle apparaten in de organisatie die zijn waargenomen bij het communiceren met het IP-adres, het bestand dat is gekoppeld aan de communicatie en de laatste waargenomen datum.

Als u op een van de apparaatnamen klikt, gaat u naar de weergave van dat apparaat, waar u gerapporteerde waarschuwingen, gedragingen en gebeurtenissen kunt blijven onderzoeken.

## <a name="related-topics"></a>Verwante onderwerpen

- [De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen](alerts-queue.md)
- [Waarschuwingen voor Microsoft Defender voor eindpunten beheren](manage-alerts.md)
- [Microsoft Defender onderzoeken voor eindpuntwaarschuwingen](investigate-alerts.md)
- [Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt](investigate-files.md)
- [Apparaten onderzoeken in de lijst Microsoft Defender voor eindpuntapparaten](investigate-machines.md)
- [Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt](investigate-domain.md)
- [Een gebruikersaccount onderzoeken in Microsoft Defender voor Eindpunt](investigate-user.md)
