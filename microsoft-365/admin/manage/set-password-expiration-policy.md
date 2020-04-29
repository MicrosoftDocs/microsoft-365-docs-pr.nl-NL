---
title: 'Het wachtwoordverloopbeleid voor uw organisatie instellen:'
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Informatie over het instellen van een verloopbeleid voor wachtwoorden voor uw bedrijf in het Microsoft 365-beheercentrum. '
ms.openlocfilehash: dd925ee3a5d2aadb07dceed5a0e896e77921e2a1
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901008"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>Het wachtwoordverloopbeleid voor uw organisatie instellen:

Dit artikel is bedoeld voor personen die het wachtwoordverloopbeleid voor een bedrijf, school of non-profitorganisatie opstellen.  

Als u een gebruiker bent, bent u niet gemachtigd om uw wachtwoord zo in te stellen dat het nooit verloopt. Vraag de technische ondersteuning van uw werk of school om de stappen in dit artikel voor u uit te voeren.

Als beheerder kunt u instellen dat gebruikerswachtwoorden na een bepaald aantal dagen verlopen of dat deze nooit verlopen. 

> [!Tip]
> Wachtwoorden verlopen standaard na 90 dagen. Recent onderzoek geeft sterk aan dat verplichte wachtwoordwijzigingen meer kwaad dan goed doen. Gebruikers kiezen dan voor zwakkere wachtwoorden, hergebruik van wachtwoorden of ze werken oude wachtwoorden bij op een manier die eenvoudig te raden is voor hackers. Als u de wachtwoorden instelt om nooit te verlopen, raden we u aan [meervoudige verificatie](../security-and-compliance/set-up-multi-factor-authentication.md) in te schakelen.

Volg onderstaande stappen als u wilt instellen dat gebruikerswachtwoorden na een bepaalde tijd verlopen.
> [!IMPORTANT]
> Alleen [globale beheerders](../add-users/about-admin-roles.md) kunnen deze stappen uitvoeren.
  
1. Ga in het beheercentrum naar **Instellingen** \> **Instellingen**.

2. Ga naar de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Beveiliging en privacy</a>.
 Als u geen globale beheerder bent, ziet u de optie Beveiliging en privacy niet.
  
3. Selecteer **Verloopbeleid wachtwoorden**.
  
4. Als u niet wilt dat gebruikers hun wachtwoorden moeten wijzigen, selecteert u het selectievakje naast **Gebruikerswachtwoorden instellen om na een aantal dagen te verlopen**.
  
5. Geef op hoe vaak wachtwoorden moeten verlopen. Kies een aantal dagen tussen 14 en 730.
  
6. Geef in het tweede vak op wanneer gebruikers een melding ontvangen over het verlopen van het wachtwoord en selecteer vervolgens **Opslaan**. Kies een aantal dagen tussen 1 en 30.
    
7. Wanneer het wachtwoord van de gebruiker verloopt, krijgt deze een melding die wordt weergegeven in de rechterbenedenhoek van het scherm.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>Belangrijke dingen die u moet weten over de functie voor verlopen wachtwoorden

Hier volgen enkele belangrijke punten over de huidige werking van deze functie sinds januari 2018:
  
- Personen die alleen gebruikmaken van de Outlook-app worden niet gedwongen hun Microsoft 365-beheerderswachtwoord opnieuw in te stellen voordat het in de cache is verlopen. Dit kan enkele dagen na de feitelijke verloopdatum in beslag nemen. Op beheerdersniveau is er geen tijdelijke oplossing voor dit probleem.
    
- Gebruikers ontvangen geen melding per e-mail dat hun wachtwoord binnen X aantal dagen verloopt. Wilt u deze functie gebruiken? **[Stem hier](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**
    
## <a name="prevent-last-password-from-being-used-again"></a>Voorkomen dat laatste wachtwoord opnieuw wordt gebruikt

Als u wilt voorkomen dat uw gebruikers oude wachtwoorden opnieuw gebruiken, kunt u dit in Azure AD instellen. Zie [Wachtwoordgeschiedenis afdwingen](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history).

Als een medewerker een mobiel apparaat gebruikt om toegang tot Microsoft 365 te krijgen, kunt u het wissen om ervoor te zorgen dat het wachtwoord niet meer wordt opgeslagen en vervolgens opnieuw gebruikt. Zie [Het mobiele apparaat van een voormalige werknemer wissen en blokkeren](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device) voor meer informatie.


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>Gebruikerswachtwoordhashes synchroniseren vanuit een on-premises Active Directory naar Azure AD (Microsoft 365) 

Dit artikel gaat over het instellen van het verloopbeleid voor gebruikers die alleen de cloud gebruiken (Azure AD). Dit geldt niet voor hybride-identiteitsgebruikers die gebruikmaken van wachtwoordhashsynchronisatie, Pass Through-verificatie of on-premises federatie, zoals ADFS.
  
Zie [Wachtwoordhashsynchronisatie met Azure AD Connect-synchronisatie implementeren](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) voor informatie over het synchroniseren van gebruikerswachtwoordhashes in een on-premises AD met gebruikerswachtwoordhashes in Azure AD.
