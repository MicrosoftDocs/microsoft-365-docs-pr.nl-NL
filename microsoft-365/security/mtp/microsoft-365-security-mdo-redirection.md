---
title: Accounts van Microsoft Defender voor Office 365 omleiden naar het nieuwe Microsoft 365-beveiligingscentrum
description: Omleiden van Defender voor Office 365 naar het Microsoft 365-beveiligingscentrum.
keywords: Microsoft 365-beveiligingscentrum, Aan de slag met het Microsoft 365-beveiligingscentrum, omleiding van het beveiligingscentrum
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 30fa10e23fd6a0c92bd5a56c797d3b7ff5b4bfd6
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416778"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Accounts van Microsoft Defender voor Office 365 omleiden naar het Microsoft 365-beveiligingscentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender
- Defender voor Office 365

In dit artikel wordt uitgelegd hoe u accounts kunt doorsturen naar het Microsoft 365-beveiligingscentrum door automatische omleiding van het voormalige Microsoft-beveiligings- en compliancecentrum (protection.office.com of securitycenter.microsoft.com) in te stellen naar het Microsoft 365-beveiligingscentrum (security.microsoft.com).

>[!NOTE]
> De portalomleidingsmogelijkheid is alleen beschikbaar voor klanten van Office 365 E5 en Microsoft Defender voor Office P2

## <a name="what-to-expect"></a>Wat u kunt verwachten
Wanneer automatische omleiding is ingeschakeld en actief is, worden gebruikers die toegang hebben tot de beveiligingsfuncties in Office 365 Security and Compliance (protection.office.com) automatisch doorgestuurd naar het Microsoft 365-beveiligingscentrum ( https://security.microsoft.com) .  

Meer informatie over wat er is gewijzigd: [Microsoft Defender voor Office 365 in het Microsoft 365-beveiligingscentrum.](microsoft-365-security-center-mdo.md)

Als automatische omleiding is ingeschakeld, worden gebruikers doorgestuurd naar het Microsoft 365-beveiligingscentrum wanneer ze beveiligingsfuncties in het Office 365-beveiligings- en compliancecentrum gebruiken.

Dit zijn onder andere mogelijkheden in de sectie Bedreigingsbeheer en het dashboard en rapporten van Bedreigingsbeheer. Items in het Office 365-beveiligings- en compliancecentrum die niet gerelateerd zijn aan beveiliging, worden niet omgeleid naar het Microsoft 365-beveiligingscentrum.

Items in verband met naleving vindt u in het Microsoft 365-compliancecentrum en items met betrekking tot e-mailstromen vindt u in het Exchange-beheercentrum.

Alle overige mogelijkheden, ongeacht of ze betrekking hebben op naleving of mogelijkheden die beide dienen, worden niet beïnvloed door omleiding. Er worden beveiligingswaarschuwingen van Office 365 weergegeven in zowel het Microsoft 365-beveiligingscentrum als het Office 365-beveiligings- en compliancecentrum, zonder omleiding.  

### <a name="set-up-portal-redirection"></a>Portalomleiding instellen
Om accounts te routeren naar het Microsoft 365-beveiligingscentrum op security.microsoft.com:

1. Zorg ervoor dat u een globale beheerder bent of dat u machtigingen voor beveiligingsbeheerders hebt in Azure Active Directory.
2. [Meld u](https://security.microsoft.com/) aan bij het Microsoft 365-beveiligingscentrum.
3. Ga naar **E-mailinstellingen**  >  **& omleiding van de**  >  **samenwerkingsportal.**  
4. Schakel de instelling voor automatische omleiding in op **Aan.**
5. Klik **op Inschakelen** om automatische omleiding toe te passen op de portal van het Microsoft 365-beveiligingscentrum.

> [!NOTE]
> Nadat omleiding is ingeschakeld, worden accounts in actieve sessies terwijl deze instelling is toegepast niet uit hun sessie gerouteerd en worden ze alleen doorgestuurd naar het Microsoft 365-beveiligingscentrum nadat ze hun huidige sessie hebben afgesloten en zich opnieuw hebben aangemeld.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kan ik teruggaan naar de vorige portal?
Als iets niet werkt voor u of als u iets niet kunt voltooien via de portal van het Microsoft 365-beveiligingscentrum, willen we dat graag weten via de feedbackoptie van de portal. Als u problemen hebt ondervonden met omleiding, raden we u aan rechtstreeks contact op te nemen met uw PM-vriend via een persoonlijke preview of ons te laten weten via het formulier feedback geven.

Terugkeren naar de vorige portal:

1. [Meld u aan](https://security.microsoft.com/) bij het Microsoft 365-beveiligingscentrum als globale beheerder of gebruik en account met machtigingen voor beveiligingsbeheerders in Azure Active Directory.

2. **Navigeer naar**  >  **instellingen-eindpunten**  >  **algemene**  >  **portalomleiding.**  

3. Zet de instelling voor automatische omleiding op **Uit.**

4. Klik **op Uitschakelen** & feedback te delen wanneer hier om wordt gevraagd.

Deze instelling kan op elk moment opnieuw worden ingeschakeld.

Als de account is uitgeschakeld, worden deze niet meer doorvergeleid naar security.microsoft.com en hebt u weer toegang tot de voormalige portal, securitycenter.windows.com of securitycenter.microsoft.com.

## <a name="related-information"></a>Gerelateerde informatie
- [Overzicht van Microsoft 365-beveiligingscentrum](overview-security-center.md)
- [Microsoft Defender voor eindpunt in het Microsoft 365-beveiligingscentrum](microsoft-365-security-center-mde.md)
- [Microsoft levert geïntegreerde SIEM en XDR om beveiligingsbewerkingen te moderniseren](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR versus SIEM infographic](https://afrait.com/blog/xdr-versus-siem/) 
- [De nieuwe Defender](https://afrait.com/blog/the-new-defender/) 
- [Over Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft-beveiligingsportals en -beheercentra](portals.md)