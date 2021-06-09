---
title: Accounts omleiden van Office 365 beveiligings- en compliancecentrum naar de nieuwe Microsoft 365 Defender
description: Omleiden van defender voor Office 365 naar Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Aan de slag met Microsoft 365 Defender, omleiding van het beveiligingscentrum
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842516"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>Accounts omleiden van Office 365 beveiligings- en compliancecentrum naar Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender
- Defender voor Office 365

In dit artikel wordt uitgelegd hoe u accounts kunt doorsturen naar Microsoft 365 Defender door automatische omleiding in te stellen van het voormalige Office 365 Security and Compliance Center (protection.office.com) naar Microsoft 365 Defender (security.microsoft.com).

## <a name="what-to-expect"></a>Wat u kunt verwachten
Wanneer automatische omleiding is ingeschakeld en actief is, worden gebruikers die toegang hebben tot de beveiligingsgerelateerde mogelijkheden in Office 365 Security and Compliance (protection.office.com), automatisch doorgestuurd naar Microsoft 365 Defender ( https://security.microsoft.com) .  

Meer informatie over wat er is gewijzigd: [Microsoft Defender voor Office 365 in Microsoft 365 Defender.](microsoft-365-security-center-mdo.md)

Wanneer automatische omleiding is ingeschakeld, worden gebruikers doorgestuurd naar Microsoft 365 Defender wanneer ze beveiligingsfuncties gebruiken in het Office 365 Beveiligings- en compliancecentrum.

Deze omvatten mogelijkheden in de sectie Bedreigingsbeheer en het dashboard bedreigingsbeheer en rapporten. Items in het Office 365 beveiligings- en compliancecentrum die geen verband houden met beveiliging, worden niet omgeleid naar Microsoft 365 Defender.

Compliancegerelateerde items vindt u in het Microsoft 365 compliancecentrum en gerelateerde items voor e-mailstroom vindt u in het Exchange beheercentrum.

Alle andere mogelijkheden, ongeacht of deze betrekking hebben op naleving of mogelijkheden die beide van pas komen, worden niet beïnvloed door omleiding. Office 365 beveiligingswaarschuwingen worden weergegeven in zowel Microsoft 365 Defender als Office 365 beveiligings- en compliancecentrum, zonder omleiding.  

### <a name="set-up-portal-redirection"></a>Portalomleiding instellen
Als u wilt beginnen met het routeren van accounts Microsoft 365 Defender op security.microsoft.com:

1. Zorg ervoor dat u een globale beheerder bent of beveiligingsbeheerdersmachtigingen hebt in Azure Active Directory.
2. [Meld u aan](https://security.microsoft.com/) bij Microsoft 365 Defender.
3. Navigeer **naar Instellingen**  >  **e-mail & portal**  >  **omleiding van de portal voor samenwerking.**  
4. Schakel de instelling Automatische omleiding in op **Aan**.
5. Klik **op Inschakelen** om automatische omleiding toe te passen op Microsoft 365 Defender.

> [!NOTE]
> Nadat omleiding is ingeschakeld, worden accounts in actieve sessies, terwijl deze instelling is toegepast, niet uit hun sessie weggestuurd en worden ze alleen doorgestuurd naar Microsoft 365 Defender nadat ze hun huidige sessie hebben afgesloten en zich opnieuw hebben aangemeld.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kan ik teruggaan naar het gebruik van de voormalige portal?
Als iets niet werkt voor u of als er iets is dat u niet kunt voltooien via Microsoft 365 Defender, willen we dit horen met de feedbackoptie voor de portal. Als u problemen hebt ondervonden met omleiding, laat het ons dan weten.

Terugkeren naar de voormalige portal:

1. [Meld u](https://security.microsoft.com/) aan bij Microsoft 365 Defender als globale beheerder of gebruik en account met machtigingen voor beveiligingsbeheerders in Azure Active Directory.

2. Navigeer **naar Instellingen**  >  **e-mail & portal**  >  **omleiding van de portal voor samenwerking.**   

3. Schakel de instelling Automatische omleiding in op **Uit.**

4. Klik **op Uitschakelen** & feedback delen wanneer u daarom wordt gevraagd.

Deze instelling kan op elk moment opnieuw worden ingeschakeld.

Nadat accounts zijn uitgeschakeld, worden accounts niet meer doorgeleid naar security.microsoft.com en hebt u opnieuw toegang tot de voormalige portal, securitycenter.windows.com of securitycenter.microsoft.com.

## <a name="related-information"></a>Gerelateerde informatie
- [Microsoft 365 Overzicht van Defender](overview-security-center.md)
- [Microsoft Defender voor Eindpunt in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft levert geïntegreerde SIEM en XDR om beveiligingsbewerkingen te moderniseren](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR versus SIEM infographic](https://afrait.com/blog/xdr-versus-siem/) 
- [De Nieuwe Defender](https://afrait.com/blog/the-new-defender/) 
- [Over Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft-beveiligingsportalen en beheercentra](portals.md)
