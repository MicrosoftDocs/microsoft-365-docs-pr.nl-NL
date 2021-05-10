---
title: Accounts omleiden van Microsoft Defender voor Office 365 naar het nieuwe Microsoft 365 beveiligingscentrum
description: Omleiden van defender voor Office 365 naar het Microsoft 365 beveiligingscentrum.
keywords: Microsoft 365 beveiligingscentrum, Aan de slag met het Microsoft 365 beveiligingscentrum, omleiding van het beveiligingscentrum
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
ms.openlocfilehash: 40d86f9f3a4896bbe788f0a9894a7e08efe3a690
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301726"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Accounts omleiden van Microsoft Defender voor Office 365 naar het Microsoft 365 beveiligingscentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender
- Defender voor Office 365

In dit artikel wordt uitgelegd hoe u accounts kunt doorsturen naar het Microsoft 365-beveiligingscentrum door automatische omleiding vanuit het voormalige Microsoft-beveiligings- en compliancecentrum (protection.office.com of securitycenter.microsoft.com) in te stellen naar het Microsoft 365-beveiligingscentrum (security.microsoft.com).

## <a name="what-to-expect"></a>Wat u kunt verwachten
Wanneer automatische omleiding is ingeschakeld en actief is, worden gebruikers die toegang hebben tot de beveiligingsgerelateerde mogelijkheden in Office 365 Security and Compliance (protection.office.com), automatisch doorgestuurd naar het Microsoft 365-beveiligingscentrum ( https://security.microsoft.com) .  

Meer informatie over wat er is gewijzigd: [Microsoft Defender voor Office 365 in het Microsoft 365 beveiligingscentrum.](microsoft-365-security-center-mdo.md)

Wanneer automatische omleiding is ingeschakeld, worden gebruikers doorgestuurd naar Microsoft 365 beveiligingscentrum wanneer ze beveiligingsfuncties gebruiken in het Office 365 Beveiligings- en compliancecentrum.

Deze omvatten mogelijkheden in de sectie Bedreigingsbeheer en het dashboard bedreigingsbeheer en rapporten. Items in het Office 365 beveiligings- en compliancecentrum die geen verband houden met beveiliging, worden niet omgeleid naar het Microsoft 365 beveiligingscentrum.

Compliancegerelateerde items vindt u in het Microsoft 365 compliancecentrum en gerelateerde items voor e-mailstroom vindt u in het Exchange beheercentrum.

Alle andere mogelijkheden, ongeacht of deze betrekking hebben op naleving of mogelijkheden die beide van pas komen, worden niet beïnvloed door omleiding. Office 365 beveiligingswaarschuwingen worden weergegeven in zowel het Microsoft 365 beveiligingscentrum als Office 365 beveiligings- en compliancecentrum, zonder omleiding.  

### <a name="set-up-portal-redirection"></a>Portalomleiding instellen
Als u wilt beginnen met het routeren van accounts naar Microsoft 365 beveiligingscentrum op security.microsoft.com:

1. Zorg ervoor dat u een globale beheerder bent of beveiligingsbeheerdersmachtigingen hebt in Azure Active Directory.
2. [Meld u](https://security.microsoft.com/) aan bij het Microsoft 365 beveiligingscentrum.
3. Navigeer **naar Instellingen**  >  **e-mail & portal**  >  **omleiding van de portal voor samenwerking.**  
4. Schakel de instelling Automatische omleiding in op **Aan**.
5. Klik **op Inschakelen** om automatische omleiding toe te passen op Microsoft 365 portal van het beveiligingscentrum.

> [!NOTE]
> Nadat omleiding is ingeschakeld, worden accounts in actieve sessies terwijl deze instelling is toegepast, niet uit hun sessie weggestuurd en worden ze alleen doorgestuurd naar het Microsoft 365-beveiligingscentrum nadat ze hun huidige sessie hebben afgesloten en zich opnieuw hebben aangemeld.

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kan ik teruggaan naar het gebruik van de voormalige portal?
Als iets niet werkt voor u of als er iets is dat u niet kunt voltooien via de portal van het Microsoft 365-beveiligingscentrum, willen we dit horen met de feedbackoptie voor de portal. Als u problemen hebt ondervonden met omleiding, raden we u aan rechtstreeks contact op te nemen met uw PM-vriend via een privévoorbeeld of ons dit te laten weten via het formulier Feedback indienen.

Terugkeren naar de voormalige portal:

1. [Meld u aan](https://security.microsoft.com/) bij het Microsoft 365 beveiligingscentrum als globale beheerder of gebruik en account met machtigingen voor beveiligingsbeheerders in Azure Active Directory.

2. **Navigeer naar Instellingen** algemene portal  >  **omleiding van**  >    >  **eindpunten**.  

3. Schakel de instelling Automatische omleiding in op **Uit.**

4. Klik **op Uitschakelen** & feedback delen wanneer u daarom wordt gevraagd.

Deze instelling kan op elk moment opnieuw worden ingeschakeld.

Nadat accounts zijn uitgeschakeld, worden accounts niet meer doorgeleid naar security.microsoft.com en hebt u opnieuw toegang tot de voormalige portal- securitycenter.windows.com of securitycenter.microsoft.com.

## <a name="related-information"></a>Gerelateerde informatie
- [Overzicht van Microsoft 365-beveiligingscentrum](overview-security-center.md)
- [Microsoft Defender voor Eindpunt in het Microsoft 365 beveiligingscentrum](microsoft-365-security-center-mde.md)
- [Microsoft levert geïntegreerde SIEM en XDR om beveiligingsbewerkingen te moderniseren](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR versus SIEM infographic](https://afrait.com/blog/xdr-versus-siem/) 
- [De Nieuwe Defender](https://afrait.com/blog/the-new-defender/) 
- [Over Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft-beveiligingsportalen en beheercentra](portals.md)
