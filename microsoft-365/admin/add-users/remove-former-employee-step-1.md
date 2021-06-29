---
title: Stap 1 - Een werknemer stoppen met aanmelden bij Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Een voormalige werknemer blokkeren om zich aan te melden en de toegang tot Microsoft 365 blokkeren.
ms.openlocfilehash: 58b65a0a886460e8be01635c857433773cfc9059
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177115"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>Stap 1: voorkomen dat een voormalige werknemer zich aanlogt en de toegang tot Microsoft 365 services blokkeert

Als u de aanmeldingstoegang van een gebruiker onmiddellijk wilt voorkomen, moet u het wachtwoord opnieuw instellen. In deze stap dwingt u de gebruiker af te melden van Microsoft 365.

> [!NOTE]
> U moet een globale beheerder zijn om de aanmelding voor andere beheerders te starten. Voor niet-beheerdersgebruikers kunt u een gebruikerbeheerder of een gebruiker van de helpdeskbeheerder gebruiken om deze actie uit te voeren. [Meer informatie over de beheerdersrollen](about-admin-roles.md)

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Schakel het vakje naast de naam van de gebruiker in en selecteer vervolgens **Wachtwoord opnieuw instellen.**
3. Voer een nieuw wachtwoord in en selecteer Vervolgens **Opnieuw instellen.** (Verzend het niet naar hen.)
4. Selecteer de naam van de gebruiker om naar het eigenschappenvenster te gaan en selecteer op het tabblad **Account** de optie **Afloggen van alle sessies.**

Binnen een uur - of nadat ze de huidige Microsoft 365 pagina waarin ze zich hebben geplaatst - worden ze gevraagd zich opnieuw aan te melden. Een toegangs token is goed voor een uur, dus de tijdlijn is afhankelijk van hoeveel tijd er nog over is op dat token en of ze buiten hun huidige webpagina navigeren.
  
> [!IMPORTANT]
> Als de gebruiker zich in webversie van Outlook, klikt u gewoon in zijn postvak en wordt deze mogelijk niet onmiddellijk uit het postvak geschopt. Zodra ze een andere tegel selecteren, zoals OneDrive of de browser vernieuwen, wordt de aanmelding gestart.
  
Zie de [cmdlet Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) als u PowerShell wilt gebruiken om een gebruiker onmiddellijk af te melden.
  
Zie [Wat u moet weten over het beëindigen van een sessie van een werknemer](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session) voor meer informatie over hoe lang het duurt om iemand de toegang tot e-mail te ontzeggen.

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>De toegang van een voormalige werknemer tot Microsoft 365 blokkeren

> [!IMPORTANT]
 > Het blokkeren van een account kan tot 24 uur duren. Als u de aanmeldingstoegang van een gebruiker onmiddellijk wilt voorkomen, volgt u de bovenstaande stappen en stelt u het wachtwoord opnieuw in.

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
2. Selecteer de naam van de werknemer die u wilt blokkeren en selecteer onder de naam van de gebruiker het symbool voor **Deze gebruiker blokkeren.**
3. Selecteer **De gebruiker blokkeren om zich aan te melden** en selecteer opslaan. 

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>De toegang van een voormalige werknemer tot e-mail (Exchange Online) blokkeren

Als u e-mail hebt als onderdeel van uw Microsoft 365-abonnement, meld u dan aan bij het Exchange-beheercentrum en volg deze stappen om te blokkeren dat uw voormalige werknemer toegang heeft tot zijn of haar e-mail.
  
1. Ga naar het <a href="https://admin.exchange.microsoft.com/" target="_blank">Exchange-beheercentrum</a>.
2. Ga in het Exchange-beheercentrum naar **Ontvangers** \> **Postvakken**.
3. Dubbelklik op de gebruiker en ga naar **Instellingen voor e-mail-apps beheren** onder **E-mail-apps.** Schakel **de** schuifregelaar voor alle opties uit. **Mobile (Exchange ActiveSync)**, **webversie van Outlook**, **Outlook desktop (MAPI)**, **Exchange webservices**, **POP3** en **IMAP**.
4. Kies **Opslaan**.
