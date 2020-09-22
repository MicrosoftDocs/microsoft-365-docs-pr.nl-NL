---
title: antiphishingfuncties voor ATP in Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5076d0f6-7a59-4d6c-bd07-ba95033f0682
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lees meer over de functies die deel uitmaken van Office 365 Advanced Threat Protection ter bescherming tegen de bescherming tegen de bescherming tegen de bescherming tegen de bescherming tegen producties & spear phishing-aanvallen.
ms.openlocfilehash: db1587d0cd60dc94e79b1498e000e63aa2a5ceac
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199061"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>antiphishingfuncties voor ATP in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


ATP anti-phishing is onderdeel van [Office 365 Advanced Threat Protection](office-365-atp.md). Als u op een anti-virus van ATP bent, past u een reeks machine leer modellen samen met imitatie detectie algoritmen voor inkomende berichten ter bescherming tegen grondstoffen en spear phishing-aanvallen. Alle berichten zijn onderhevig aan een uitgebreide set machine learning-modellen die zijn opgeleid voor het detecteren van phishingberichten, samen met een set geavanceerde algoritmen die worden gebruikt voor het beschermen tegen verschillende aanvallen van gebruikers en domein imitatie. ATP anti-phishing beschermt uw organisatie op basis van policies die zijn ingesteld door uw Office 365-globale beheerder of beveiligingsbeheerder.
  
Zie [anti phishingfilter instellen in Office 365](set-up-anti-phishing-policies.md)voor meer informatie.
  
> [!NOTE]
> ATP anti-phishing is alleen beschikbaar in Advanced Threat Protection, dat deel uitmaakt van een abonnement, zoals [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 education A5, enzovoort. Als uw organisatie een Office 365-abonnement heeft dat geen Office 365-ATP bevat, kunt u ATP kopen als een invoegtoepassing. Zie voor meer informatie [office 365 Advanced Threat Protection-abonnementen en-prijzen](https://products.office.com/exchange/advance-threat-protection) en de beschrijving van de [Office 365 Advanced Threat Protection-Service](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="how-atp-anti-phishing-works"></a>De werking van ATP anti phishing

ATP anti-phishing controleert inkomende berichten voor indicatoren die het bericht kan phishing. Telkens wanneer een gebruiker is onderworpen aan een ATP-beleid (veilige bijlagen, veilige koppelingen of anti-phishing), wordt het inkomende bericht geëvalueerd door meerdere machine learning modellen waarmee het bericht wordt geanalyseerd om te bepalen of het beleid van toepassing is op het bericht en dat de juiste actie wordt uitgevoerd op basis van het geconfigureerde beleid.
  
Met anti-phishing in Office 365 kunnen globale beheerders van Office of beveiligingsbeheerders beleidsregels definiëren die bescherming bieden tegen phishing-aanvallen, waaronder imitatie van gebruikers of domeinen. (of beide). Globale beheerders van Office 365 of beveiligingsbeheerders definiëren binnen het beleid welke gebruikers en domeinen moeten worden beveiligd tegen imitatie aanvallen via een vaste lijst met gebruikers of domeinen, of via postvak Intelligence. Postvak intelligentie is een uitgebreide uitleg van e-mail gewoonten en persoonlijke contactpersonen van een gebruiker. Met ATP leert u hoe elke afzonderlijke gebruiker communiceert met andere gebruikers binnen en buiten de organisatie en een kaart van deze relaties bouwt. In deze kaart mag ATP worden gebruikt voor meer informatie over hoe u ervoor zorgt dat de juiste berichten als imitatie worden geïdentificeerd.
  
U kunt op een specifieke groep personen of groepen in uw organisatie of in een volledig domein of al uw aangepaste domeinen toepassen. Zie [anti phishingfilter instellen in Office 365](set-up-anti-phishing-policies.md)voor meer informatie.
  
## <a name="how-to-get-atp-anti-phishing"></a>Hoe kan ik het anti-phishing van ATP

De functies van de ATP-anti ervaring maken deel uit van [Advanced Threat Protection](office-365-atp.md). Er is echter wel een anti-phishing-bescherming van ATP van toepassing wanneer beleidsregels worden gedefinieerd. (Één voorbeeld is een beleid op basis van imitatie.) Zie [anti phishingfilter instellen in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Hoe weet u of ATP anti-phishing is geïnstalleerd?

U moet een anti-phishingfilter-beleid definiëren om de bescherming van kracht te laten worden. Controleer eerst of de beveiliging is ingeschakeld.

Daarnaast zijn er rapporten beschikbaar om aan te geven hoe de service werkt voor uw organisatie. Zie [rapporten weergeven voor Office 365 Advanced Threat Protection voor](view-reports-for-atp.md)meer informatie.

Voor een bepaalde gebruiker moet de bewerkings modellen van een ATP-computer worden geactiveerd voor een bepaalde gebruiker, moet de gebruiker een deel uitmaken van een gedefinieerde, [veilige](atp-safe-attachments.md) [of vrije](atp-safe-links.md)lijst met ATP. 

In de volgende tabel ziet u enkele voorbeelden van scenario's. In elk van deze voorbeelden wordt de organisatie van Office 365 Enterprise E5 gebruikt, waaronder Advanced Threat Protection.

****

|Voorbeeld van scenario|Is er sprake van een anti-phishing van ATP op dit geval?|
|---|---|
|De organisatie van de Pat heeft Office 365 Enterprise E5, maar niemand heeft beleidsregels gedefinieerd voor veilige documenten met ATP, veilige koppelingen voor ATP of nog geavanceerde phishing.|Nee. Hoewel de functie beschikbaar is, moet ten minste één ATP-beleid zijn gedefinieerd om de bewerkings modellen van de ATP machine te kunnen gebruiken. Voor imitatie moet een ATP anti-phishingfilter ook plaatsvinden.|
|Lee is een werknemer in de verkoopafdeling bij contoso. Voor de organisatie van Lee is een ATP anti phishing-beleid ter plaatse bedoeld voor de financiering van medewerkers.|Nee. In dit geval zijn de werknemers op basis van ATP (computermodellen en imitatie bescherming) van toepassing op werknemers, maar andere werknemers, waaronder de afdeling verkoop.|
|Gisteren, een Office 365-beheerder van de organisatie van de Jean, die van toepassing is op alle werknemers. Eerder vandaag heeft Jean een e-mailbericht ontvangen met een imiteren die onder de beleidsregels valt.|Ja. In dit voorbeeld heeft Jean een licentie voor Advanced Threat Protection en is er een ATP anti-phishingfilter met de instelling Jean is gedefinieerd. Het duurt doorgaans ongeveer dertig minuten voordat een nieuw beleid is doorgevoerd in de datacenters; Aangezien een dag in dit geval is verstreken, moet het beleid van kracht zijn.|
|

## <a name="related-topics"></a>Verwante onderwerpen

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Beveiliging tegen phishing in Office 365](anti-phishing-protection.md)
  
[Anti phishingfilter instellen in Office 365](set-up-anti-phishing-policies.md)
  
[Veilige koppelingen voor ATP in Office 365](atp-safe-links.md)
  
[Beleidsregels voor veilige koppelingen instellen in Office 365](set-up-atp-safe-links-policies.md)
  
[In Office 365](atp-safe-attachments.md)
  
[Beleidsregels voor veilige bijlagen instellen in Office 365](set-up-atp-safe-attachments-policies.md)
  
[De rapporten voor Advanced Threat Protection weergeven](view-reports-for-atp.md)
