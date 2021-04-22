---
title: Microsoft Defender voor eindpuntdomeinen onderzoeken
description: Gebruik de onderzoeksopties om te zien of apparaten en servers met schadelijke domeinen hebben gecommuniceerd.
keywords: domein, domein, kwaadwillend domein, Microsoft Defender voor eindpunt, waarschuwing, URL onderzoeken
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
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 7826229ba67384137c033745a5b85e557fc9c4a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933467"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Een domein onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

Onderzoek een domein om te zien of apparaten en servers in uw bedrijfsnetwerk hebben gecommuniceerd met een bekend kwaadwillend domein.

U kunt een domein onderzoeken met behulp van de zoekfunctie of door te klikken op een domeinkoppeling vanuit de **apparaattijdlijn.**

In de URL-weergave ziet u informatie uit de volgende secties:

- URL-details, Contactpersonen, Nameservers
- Waarschuwingen met betrekking tot deze URL 
- URL in organisatie
- Meest recente waargenomen apparaten met URL

## <a name="url-worldwide"></a>URL wereldwijd

De **sectie URL Worldwide** bevat de URL, een koppeling naar meer informatie bij Whois, het aantal gerelateerde geopende incidenten en het aantal actieve waarschuwingen.

## <a name="incident"></a>Incident

Op **de kaart Incident** wordt een staafdiagram weergegeven met alle actieve waarschuwingen in incidenten van de afgelopen 180 dagen.

## <a name="prevalence"></a>Prevalentie

De **kaart Prevalentie** bevat details over de prevalentie van de URL binnen de organisatie, over een bepaalde periode.

Hoewel de standaardperiode de afgelopen 30 dagen is, kunt u het bereik aanpassen door de pijl naar beneden in de hoek van de kaart te selecteren. Het kortste bereik dat beschikbaar is voor de prevalentie van de afgelopen dag, terwijl het langste bereik de afgelopen 6 maanden is.

## <a name="alerts"></a>Waarschuwingen

Het **tabblad** Waarschuwingen bevat een lijst met waarschuwingen die zijn gekoppeld aan de URL. De tabel die hier wordt weergegeven, is een gefilterde versie van de waarschuwingen die zichtbaar zijn in het waarschuwingswachtrijscherm, met alleen waarschuwingen die zijn gekoppeld aan het domein, de ernst, status, het bijbehorende incident, de classificatie, de onderzoeksstatus en meer.

Het tabblad Waarschuwingen kan worden aangepast om meer of minder informatie weer te geven door kolommen aanpassen te **selecteren** in het actiemenu boven de kolomkoppen. Het aantal weergegeven items kan ook worden aangepast door **items per pagina in** hetzelfde menu te selecteren.

## <a name="observed-in-organization"></a>Waargenomen in organisatie

Het **tabblad Waargenomen in organisatie** biedt een chronologische weergave van de gebeurtenissen en bijbehorende waarschuwingen die zijn waargenomen op de URL. Dit tabblad bevat een tijdlijn en een aanpasbare tabel met gebeurtenisdetails, zoals de tijd, het apparaat en een korte beschrijving van wat er is gebeurd. 

U kunt gebeurtenissen uit verschillende perioden bekijken door de datums in te geven in de tekstvelden boven de tabelkoppen. U kunt ook het tijdbereik aanpassen door verschillende gebieden van de tijdlijn te selecteren.

**Een domein onderzoeken:**

1. Selecteer **URL** in **de** vervolgkeuzelijst Zoekbalk.
2. Voer de URL in het **veld Zoeken** in.
3. Klik op het zoekpictogram of druk op **Enter.** Details over de URL worden weergegeven. Opmerking: zoekresultaten worden alleen geretourneerd voor URL's die worden waargenomen in communicatie vanaf apparaten in de organisatie.
4. Gebruik de zoekfilters om de zoekcriteria te definiëren. U kunt ook het zoekvak voor de tijdlijn gebruiken om de weergegeven resultaten te filteren van alle apparaten in de organisatie die zijn waargenomen bij het communiceren met de URL, het bestand dat is gekoppeld aan de communicatie en de laatste waargenomen datum.
5. Als u op een van de apparaatnamen klikt, gaat u naar de weergave van dat apparaat, waar u gerapporteerde waarschuwingen, gedragingen en gebeurtenissen kunt blijven onderzoeken.

## <a name="related-topics"></a>Verwante onderwerpen
- [De wachtrij waarschuwingen voor Microsoft Defender voor eindpunten weergeven en ordenen](alerts-queue.md)
- [Waarschuwingen voor Microsoft Defender voor eindpunten beheren](manage-alerts.md)
- [Microsoft Defender onderzoeken voor eindpuntwaarschuwingen](investigate-alerts.md)
- [Een bestand onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt](investigate-files.md)
- [Apparaten onderzoeken in de lijst Microsoft Defender voor eindpuntapparaten](investigate-machines.md)
- [Een IP-adres onderzoeken dat is gekoppeld aan een waarschuwing van Microsoft Defender voor eindpunt](investigate-ip.md)
- [Een gebruikersaccount onderzoeken in Microsoft Defender voor Eindpunt](investigate-user.md)
