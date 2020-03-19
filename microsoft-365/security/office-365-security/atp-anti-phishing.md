---
title: ATP-anti-phishingmogelijkheden in Office 365
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
description: ATP anti-phishing is onderdeel van Office 365 Advanced Threat Protection. ATP anti-phishing past een set machine learning-modellen samen met imitatiedetectiealgoritmen toe op binnenkomende berichten om bescherming te bieden voor aanvallen op goederen en spear phishing. Alle berichten zijn onderworpen aan een uitgebreide set van machine learning modellen getraind om phishing-berichten te detecteren, samen met een set van geavanceerde algoritmen die worden gebruikt om te beschermen tegen verschillende gebruiker en domein imitatie aanvallen.
ms.openlocfilehash: eca12a1f75057aee94762a8a5eef0cceffe327d3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809855"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>ATP-anti-phishingmogelijkheden in Office 365

ATP anti-phishing is onderdeel van [Office 365 Advanced Threat Protection](office-365-atp.md). ATP anti-phishing past een set machine learning-modellen samen met imitatiedetectiealgoritmen toe op binnenkomende berichten om bescherming te bieden voor aanvallen op goederen en spear phishing. Alle berichten zijn onderworpen aan een uitgebreide set van machine learning modellen getraind om phishing-berichten te detecteren, samen met een set van geavanceerde algoritmen die worden gebruikt om te beschermen tegen verschillende gebruiker en domein imitatie aanvallen. ATP-anti-phishing beschermt uw organisatie volgens de politie die is ingesteld door uw Office 365-globale of beveiligingsbeheerders.
  
Zie [Anti-phishingbeleid instellen in Office 365](set-up-anti-phishing-policies.md)voor meer informatie.
  
> [!NOTE]
> ATP-anti-phishing is alleen beschikbaar in Advanced Threat Protection, die is opgenomen in abonnementen, zoals [Microsoft 365 Enterprise,](https://www.microsoft.com/microsoft-365/enterprise/home) [Microsoft 365 Business,](https://www.microsoft.com/microsoft-365/business)Office 365 Enterprise E5, Office 365 Education A5, enz. Als uw organisatie een Office 365-abonnement heeft dat office 365 ATP niet bevat, u ATP mogelijk als bijtelling aanschaffen. Zie [Office 365 Advanced Threat Protection-abonnementen en -prijzen](https://products.office.com/exchange/advance-threat-protection) en de beschrijving van de [Office 365 Advanced Threat Protection Service](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor meer informatie.

## <a name="how-atp-anti-phishing-works"></a>Hoe ATP anti-phishing werkt

ATP anti-phishing controleert binnenkomende berichten op indicatoren dat het bericht phishing kan zijn. Wanneer een gebruiker onder een ATP-beleid valt (veilige bijlagen, veilige links of anti-phishing) wordt het binnenkomende bericht geëvalueerd door meerdere machine learning-modellen die het bericht analyseren om te bepalen of het beleid van toepassing is op het bericht en de juiste actie is genomen op basis van het geconfigureerde beleid.
  
Atp-anti-phishing stelt office 365-beheerders of beveiligingsbeheerders in staat om beleid te definiëren dat bescherming biedt tegen phishing-aanvallen die imitatie van gebruikers of domeinen omvatten. (of beide). Globale beheerders of beveiligingsbeheerders van Office 365 definiëren binnen het beleid welke gebruikers en domeinen moeten worden beschermd tegen imitatieaanvallen met behulp van een vaste lijst met gebruikers of domeinen of met behulp van postvakinformatie. Postvakintelligentie is een geavanceerd begrip van de e-mailgewoonten en persoonlijke contacten van een gebruiker. ATP leert hoe elke individuele gebruiker communiceert met andere gebruikers binnen en buiten de organisatie en bouwt een kaart van deze relaties op. Met deze kaart kan ATP meer informatie begrijpen over hoe u ervoor zorgen dat de juiste berichten worden geïdentificeerd als imitatie.
  
ATP anti-phishing politie kan worden toegepast op een specifieke set van mensen of groepen in uw organisatie, of op een heel domein of al uw aangepaste domeinen. Zie [Anti-phishingbeleid instellen in Office 365](set-up-anti-phishing-policies.md)voor meer informatie.
  
## <a name="how-to-get-atp-anti-phishing"></a>Hoe krijg je ATP anti-phishing

ATP Anti-Phishing functies maken deel uit van [Advanced Threat Protection](office-365-atp.md); ATP-anti-phishingbescherming is echter van toepassing wanneer anti-phishingbeleid wordt gedefinieerd. (Een voorbeeld is een op imitatie gebaseerd beleid.) Zie [Anti-phishingbeleid instellen in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Hoe te weten of ATP anti-phishing is op zijn plaats

ATP anti-phishing beleid moet worden gedefinieerd om bescherming van kracht te zijn. Controleer eerst dit om te controleren of de beveiliging aanwezig is.

Daarnaast zijn er rapporten beschikbaar om te laten zien hoe de service werkt voor uw organisatie. Zie [Rapporten weergeven voor Geavanceerde bedreigingsbeveiliging van Office 365](view-reports-for-atp.md).

Om ATP-anti-phishing machine learning-modellen actief te laten zijn voor een bepaalde gebruiker, moet die gebruiker deel uitmaken van een gedefinieerde [ATP Safe-bijlagen,](atp-safe-attachments.md) [ATP Safe Links](atp-safe-links.md)of ATP Anti-Phishing-beleid. 

In de volgende tabel worden enkele voorbeeldscenario's beschreven. In elk van deze voorbeelden gebruikt de organisatie Office 365 Enterprise E5, inclusief Geavanceerde bedreigingsbeveiliging.
  
|**Voorbeeldscenario**|**Is ATP anti-phishing van toepassing in dit geval?**|
|:-----|:-----|
|Pat's organisatie heeft Office 365 Enterprise E5, maar niemand heeft een beleid voor ATP veilige bijlagen, ATP veilige links of ATP geavanceerde phishing nog niet gedefinieerd.|Nee. Hoewel de functie beschikbaar is, moet ten minste één ATP-beleid worden gedefinieerd om de ATP-machine learning-modellen te laten werken. Voor imitatie moet ook een ATP-antiphishingbeleid zijn.|
|Lee is een medewerker op de verkoopafdeling van Contoso. Lee's organisatie heeft een ATP anti-phishing beleid dat alleen geldt voor financiële werknemers.|Nee. In dit geval zou ATP anti-phishing (machinemodellen en imitatiebescherming) van toepassing zijn op financiële werknemers, maar andere werknemers, waaronder de verkoopafdeling, niet.|
|Gisteren heeft een Office 365-beheerder van de organisatie van Jean een ATP-antiphishingbeleid ingesteld dat van toepassing is op alle werknemers. Eerder vandaag ontving Jean een e-mailbericht met een imitatie die onder het beleid valt.|Ja. In dit voorbeeld heeft Jean een licentie voor Advanced Threat Protection en is een ATP-antiphishingbeleid gedefinieerd dat Jean omvat. Het duurt meestal ongeveer 30 minuten voordat een nieuw beleid van kracht wordt in datacenters; aangezien in dit geval een dag is verstreken, moet het beleid van kracht zijn.|

## <a name="related-topics"></a>Verwante onderwerpen

[Geavanceerde bedreigingsbeveiliging van Office 365](office-365-atp.md)
  
[Bescherming tegen phishing in Office 365](anti-phishing-protection.md)
  
[Anti-phishingbeleid instellen in Office 365](set-up-anti-phishing-policies.md)
  
[ATP-veilige koppelingen in Office 365](atp-safe-links.md)
  
[ATP-beleid voor veilige koppelingen instellen in Office 365](set-up-atp-safe-links-policies.md)
  
[ATP-veilige bijlagen in Office 365](atp-safe-attachments.md)
  
[ATP-beleid voor veilige bijlagen instellen in Office 365](set-up-atp-safe-attachments-policies.md)
  
[Bekijk de rapporten voor Advanced Threat Protection](view-reports-for-atp.md)
