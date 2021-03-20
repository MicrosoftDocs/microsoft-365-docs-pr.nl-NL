---
title: Accounts omleiden van Microsoft Defender voor Eindpunt naar het Microsoft 365-beveiligingscentrum
description: Accounts en sessies omleiden van het Defender voor Eindpunt naar het Microsoft 365-beveiligingscentrum.
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
ms.openlocfilehash: bdad55a98dba868d45ecea383ba379108ee5305a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906756"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a>Accounts omleiden van Microsoft Defender voor Eindpunt naar het Microsoft 365-beveiligingscentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Van toepassing op:**
- Microsoft 365 Defender
- Defender voor Eindpunt

In overeenstemming met de cross-domain-benadering van Microsoft voor bedreigingsbeveiliging met SIEM en XDR (Extended detection and response), hebben we Microsoft Defender Advanced Threat Protection omgedoopt tot Microsoft Defender voor Eindpunt en samengevoegd tot één geïntegreerde portal: het Microsoft 365-beveiligingscentrum.

In deze handleiding wordt uitgelegd hoe u accounts kunt doorsturen naar het Microsoft 365-beveiligingscentrum door automatische omleiding vanuit de voormalige Microsoft Defender voor Eindpunt-portal (securitycenter.windows.com of securitycenter.microsoft.com) in te stellen naar de Microsoft 365-portal voor beveiligingscentrum (security.microsoft.com).

> [!NOTE]
> Microsoft Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum ondersteunt het verlenen van toegang tot beheerde beveiligingsserviceproviders [(MSSP's)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) op dezelfde manier als toegang wordt verleend in het [Microsoft Defender-beveiligingscentrum.](./mssp-access.md)

## <a name="what-to-expect"></a>Wat u kunt verwachten
Wanneer automatische omleiding is ingeschakeld, worden accounts die toegang hebben tot de voormalige Microsoft Defender voor Eindpunt-portal bij securitycenter.windows.com of securitycenter.microsoft.com, automatisch doorgestuurd naar de microsoft 365-beveiligingscentrumportal op security.microsoft.com.
 
Meer informatie over wat er is gewijzigd: [Microsoft Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum.](microsoft-365-security-center-mde.md)

Dit omvat omleiding voor directe toegang tot de voormalige portal via de browser, inclusief koppelingen naar de voormalige securitycenter.windows.com-portal, zoals koppelingen in e-mailmeldingen en koppelingen die worden geretourneerd door SIEM API-oproepen.  

 Externe koppelingen van e-mailmeldingen of SIEM-API's bevatten momenteel koppelingen naar beide portals. Wanneer omleiding is ingeschakeld, verwijzen beide koppelingen naar het Microsoft 365-beveiligingscentrum totdat de oude koppeling uiteindelijk wordt verwijderd. We raden u aan de nieuwe koppeling te gebruiken die verwijst naar het Microsoft 365-beveiligingscentrum.

Raadpleeg de onderstaande tabel voor meer informatie over koppelingen en routering.
## <a name="siem-api-routing"></a>SIEM API-routering

|**Eigenschap**  |**Bestemming wanneer omleiding UIT is**  |**Doel wanneer omleiding AAN is** | 
|---------|---------|---------|
| LinkToWDATP | Waarschuwingspagina in securitycenter.windows.com | Waarschuwingspagina in security.microsoft.com  |
| IncidentLinkToWDATP | Pagina Incident in securitycenter.windows.com  | Pagina Incident in security.microsoft.com  |
| LinkToMTP | Waarschuwingspagina in security.microsoft.com | Waarschuwingspagina in security.microsoft.com  |
| IncidentLinkToMTP | Pagina Incident in security.microsoft.com  | Pagina Incident in security.microsoft.com  

## <a name="email-alert-notifications"></a>Meldingen van e-mailmeldingen

|**Eigenschap**  |**Bestemming wanneer omleiding UIT is**  |**Doel wanneer omleiding AAN is** |
|---------|---------|---------|
| Waarschuwingspagina  | Waarschuwingspagina in securitycenter.windows.com  | Waarschuwingspagina in security.microsoft.com  |
| Pagina Incident  |Pagina Incident in securitycenter.windows.com  | Pagina Incident in security.microsoft.com  
| Waarschuwingspagina in de portal van het beveiligingscentrum | Waarschuwingspagina in security.microsoft.com | Waarschuwingspagina in security.microsoft.com | 
| Pagina Incident in de portal van het beveiligingscentrum | Pagina Incident in security.microsoft.com  | Pagina Incident in security.microsoft.com  |

## <a name="when-does-this-take-effect"></a>Wanneer wordt dit van kracht? 
Wanneer deze update is ingeschakeld, kan deze update vrijwel direct van kracht worden voor sommige accounts. Het kan echter langer duren om de omleiding door te laten gaan naar elk account in uw organisatie. Accounts in actieve sessies terwijl deze instelling wordt toegepast, worden niet uit hun sessie weggestuurd en worden alleen doorgestuurd naar het Microsoft 365-beveiligingscentrum nadat ze hun huidige sessie hebben afgesloten en zich opnieuw hebben aangemeld.  

### <a name="set-up-portal-redirection"></a>Portalomleiding instellen
Als u wilt beginnen met het routeren van accounts naar het Microsoft 365-beveiligingscentrum:
1. Zorg ervoor dat u een globale beheerder bent of beveiligingsbeheerdersmachtigingen hebt in Azure Active Directory 

2. [Meld u](https://security.microsoft.com/) aan bij het Microsoft 365-beveiligingscentrum.

3. Ga naar **Instellingen**  >  **Eindpunten**  >  **Algemene**  >  **portalomleiding of** klik [hier.](https://security.microsoft.com/preferences2/portal_redirection)  

4. Schakel de instelling Automatische omleiding in op **Aan**.

5. Klik **op Inschakelen** om automatische omleiding toe te passen op de portal van het Microsoft 365-beveiligingscentrum.

>[!IMPORTANT]
>Als u deze instelling inschakelen, worden actieve gebruikerssessies niet beëindigd. Accounts die in een actieve sessie zitten terwijl deze instelling wordt toegepast, worden alleen doorgestuurd naar het Microsoft 365-beveiligingscentrum nadat ze hun huidige sessie hebben afgesloten en zich opnieuw hebben aangemeld.

>[!NOTE]
>U moet een globale beheerder zijn of beveiligingsbeheerdersmachtigingen hebben in Azure Active Directory om deze instelling in of uit te schakelen.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>Kan ik teruggaan naar het gebruik van de voormalige portal?
Als iets niet werkt voor u of als er iets is dat u niet kunt voltooien via de portal van het Microsoft 365-beveiligingscentrum, willen we dit graag horen. Als u problemen hebt ondervonden met omleiding, raden we u aan ons dit te laten weten via het formulier Feedback indienen.

Terugkeren naar de voormalige Microsoft Defender for Endpoint-portal:

1. [Meld u aan](https://security.microsoft.com/) bij het Microsoft 365-beveiligingscentrum als globale beheerder of gebruik en account met machtigingen voor beveiligingsbeheerders in Azure Active Directory.

2. Ga naar **Instellingen**  >  **Eindpunten**  >  **Algemene**  >  **portalomleiding** of [open de pagina hier.](https://security.microsoft.com/preferences2/portal_redirection)  

3. Schakel de instelling Automatische omleiding in op **Uit.**

4. Klik **op Uitschakelen** & feedback delen wanneer u daarom wordt gevraagd.

Deze instelling kan op elk moment opnieuw worden ingeschakeld. 

Nadat accounts zijn uitgeschakeld, worden accounts niet meer doorgeleid naar security.microsoft.com en hebt u opnieuw toegang tot de voormalige portal- securitycenter.windows.com of securitycenter.microsoft.com. 

## <a name="related-information"></a>Gerelateerde informatie
- [Overzicht van Microsoft 365-beveiligingscentrum](overview-security-center.md)
- [Microsoft Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum](microsoft-365-security-center-mde.md)
- [Microsoft levert geïntegreerde SIEM en XDR om beveiligingsbewerkingen te moderniseren](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR versus SIEM infographic](https://afrait.com/blog/xdr-versus-siem/) 
- [De Nieuwe Defender](https://afrait.com/blog/the-new-defender/) 
- [Over Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Microsoft-beveiligingsportalen en beheercentra](portals.md)