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
description: Meer informatie over anti-phishing-mogelijkheden die deel uitmaken van Office 365 Advanced Threat Protection om bescherming te bieden voor & spear phishing-aanvallen.
ms.openlocfilehash: dda94145dfbef7466ebd8e1fb9f01d592515f598
ms.sourcegitcommit: 5e8901e7e571f20ede04f460bd3e7077dda004ca
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2020
ms.locfileid: "44875415"
---
# <a name="atp-anti-phishing-capabilities-in-office-365"></a>antiphishingfuncties voor ATP in Office 365

ATP-antiphishing maakt deel uit van [Geavanceerde bedreigingsbeveiliging van Office 365.](office-365-atp.md) ATP anti-phishing past een set machine learning-modellen samen met imitatiedetectiealgoritmen toe op binnenkomende berichten om bescherming te bieden voor phishing-aanvallen op basis van grondstoffen en speer. Alle berichten zijn onderworpen aan een uitgebreide set van machine learning-modellen getraind om phishing-berichten te detecteren, samen met een set van geavanceerde algoritmen die worden gebruikt om te beschermen tegen verschillende gebruiker en domein imitatie aanvallen. ATP-antiphishing beschermt uw organisatie op basis van politiemensen die zijn ingesteld door uw algemene of beveiligingsbeheerders van Office 365.
  
Zie [Anti-phishingbeleid instellen in Office 365](set-up-anti-phishing-policies.md)voor meer informatie.
  
> [!NOTE]
> ATP-antiphishing is alleen beschikbaar in Advanced Threat Protection, dat is opgenomen in abonnementen, zoals [Microsoft 365 Enterprise,](https://www.microsoft.com/microsoft-365/enterprise/home) [Microsoft 365 Business,](https://www.microsoft.com/microsoft-365/business)Office 365 Enterprise E5, Office 365 Education A5, enz. Als uw organisatie een Office 365-abonnement heeft dat geen Office 365 ATP bevat, u ATP mogelijk als invoegtoepassing aanschaffen. Zie [Office 365 Advanced Threat Protection-abonnementen en -prijzen en](https://products.office.com/exchange/advance-threat-protection) de beschrijving van de [Geavanceerde bedreigingsbeveiliging van Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor geavanceerde bedreigingenservice voor meer informatie.

## <a name="how-atp-anti-phishing-works"></a>Hoe ATP anti-phishing werkt

ATP anti-phishing controleert inkomende berichten op indicatoren dat het bericht phishing kan zijn. Wanneer een gebruiker wordt gedekt door een ATP-beleid (veilige bijlagen, veilige links of anti-phishing) wordt het binnenkomende bericht geëvalueerd door meerdere machine learning-modellen die het bericht analyseren om te bepalen of het beleid van toepassing is op het bericht en de juiste actie wordt ondernomen, op basis van het geconfigureerde beleid.
  
Met ATP-antiphishing kunnen wereldwijde beheerders of beveiligingsbeheerders van Office 365 beleid definiëren dat bescherming biedt tegen phishing-aanvallen die imitatie van gebruikers of domeinen omvatten. (of beide). Globale beheerders of beveiligingsbeheerders van Office 365 definiëren binnen het beleid welke gebruikers en domeinen moeten worden beschermd tegen imitatieaanvallen met behulp van een vaste lijst met gebruikers of domeinen of door postvakinformatie te gebruiken. Mailbox intelligence is een geavanceerd begrip van de e-mailgewoonten van een gebruiker en persoonlijke contacten. ATP leert hoe elke individuele gebruiker communiceert met andere gebruikers binnen en buiten de organisatie en bouwt een kaart op van deze relaties. Deze kaart stelt ATP in staat om meer details te begrijpen over hoe u ervoor zorgen dat de juiste berichten worden geïdentificeerd als imitatie.
  
ATP-antiphishingpolitie kan worden toegepast op een specifieke groep mensen of groepen in uw organisatie, of op een heel domein of al uw aangepaste domeinen. Zie [Anti-phishingbeleid instellen in Office 365](set-up-anti-phishing-policies.md)voor meer informatie.
  
## <a name="how-to-get-atp-anti-phishing"></a>Hoe atp anti-phishing te krijgen

ATP Anti-Phishing-functies maken deel uit van [Advanced Threat Protection;](office-365-atp.md) ATP-bescherming tegen phishing is echter van toepassing wanneer het anti-phishingbeleid wordt gedefinieerd. (Een voorbeeld is een op imitatie gebaseerd beleid.) Zie [Anti-phishingbeleid instellen in Office 365](set-up-anti-phishing-policies.md).
  
## <a name="how-to-know-if-atp-anti-phishing-is-in-place"></a>Hoe weet je of ATP anti-phishing aanwezig is

Atp anti-phishing beleid moet worden gedefinieerd om bescherming van kracht te zijn. Controleer dit eerst om te controleren of de beveiliging is op zijn plaats.

Daarnaast zijn rapporten beschikbaar om te laten zien hoe de service werkt voor uw organisatie. Zie [Rapporten voor Geavanceerde bedreigingsbeveiliging van Office 365 weergeven voor](view-reports-for-atp.md)meer informatie.

Als ATP-modellen voor machine learning-antiphishing actief zijn voor een bepaalde gebruiker, moet die gebruiker deel uitmaken van een gedefinieerd [ATP Safe-bijlagen,](atp-safe-attachments.md) [ATP Safe Links](atp-safe-links.md)of ATP Anti-Phishing-beleid. 

In de volgende tabel worden enkele voorbeeldscenario's beschreven. In elk van deze voorbeelden gebruikt de organisatie Office 365 Enterprise E5, waaronder Geavanceerde bedreigingsbescherming.
  
|**Voorbeeldscenario**|**Is ATP anti-phishing van toepassing in dit geval?**|
|:-----|:-----|
|Pat's organisatie heeft Office 365 Enterprise E5, maar niemand heeft beleid gedefinieerd voor ATP-veilige bijlagen, ATP-veilige links of ATP advanced phishing.|Nee. Hoewel de functie beschikbaar is, moet ten minste één ATP-beleid worden gedefinieerd om de ATP-machine learning-modellen te laten werken. Voor imitatie moet er ook een ATP-anti-phishingbeleid zijn.|
|Lee is een medewerker op de verkoopafdeling van Contoso. Lee's organisatie heeft een ATP anti-phishing beleid in de plaats die alleen van toepassing is op de financiering van werknemers.|Nee. In dit geval zou ATP-anti-phishing (machinemodellen en imitatiebeveiliging) van toepassing zijn op werknemers in de financiële sector, maar andere werknemers, waaronder de verkoopafdeling, niet.|
|Gisteren heeft een Office 365-beheerder van de organisatie van Jean een ATP-antiphishingbeleid ingesteld dat van toepassing is op alle werknemers. Eerder vandaag ontving Jean een e-mailbericht met daarin een imitatie die onder het beleid valt.|Ja. In dit voorbeeld heeft Jean een licentie voor Advanced Threat Protection en is een ATP-antiphishingbeleid dat Jean omvat gedefinieerd. Het duurt meestal ongeveer 30 minuten voordat een nieuw beleid van kracht wordt in verschillende datacenters; aangezien in dit geval een dag is verstreken, moet het beleid van kracht zijn.|

## <a name="related-topics"></a>Verwante onderwerpen

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Beveiliging tegen phishing in Office 365](anti-phishing-protection.md)
  
[Antiphishingbeleid instellen in Office 365](set-up-anti-phishing-policies.md)
  
[Veilige ATP-koppelingen in Office 365](atp-safe-links.md)
  
[Beleid voor veilige koppelingen atp instellen in Office 365](set-up-atp-safe-links-policies.md)
  
[ATP-veilige bijlagen in Office 365](atp-safe-attachments.md)
  
[Beleid voor atp-veilige bijlagen instellen in Office 365](set-up-atp-safe-attachments-policies.md)
  
[Bekijk de rapporten voor Advanced Threat Protection](view-reports-for-atp.md)
