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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Informatie over het instellen van een verloopbeleid voor wachtwoorden voor uw bedrijf in het Microsoft 365-beheercentrum.
ms.openlocfilehash: 74b23b4a1b67ecd5c9199388985e8e38c3231239
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221821"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>Het wachtwoordverloopbeleid voor uw organisatie instellen:

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](../microsoft-365-admin-center-preview.md?view=o365-worldwide).

::: moniker-end

## <a name="before-you-begin"></a>Voordat u begint

Dit artikel is bedoeld voor personen die het wachtwoordverloopbeleid voor een bedrijf, school of non-profitorganisatie opstellen. Voor het uitvoeren van deze stappen moet u zich aanmelden met uw Microsoft 365-beheerdersaccount. [Wat is een beheerdersaccount?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).

Je moet een [globale beheerder](../add-users/about-admin-roles.md) zijn om deze stappen uit te voeren.

Als u een gebruiker bent, bent u niet gemachtigd om uw wachtwoord zo in te stellen dat het nooit verloopt. Vraag de technische ondersteuning van uw werk of school om de stappen in dit artikel voor u uit te voeren.

Als beheerder kunt u instellen dat gebruikerswachtwoorden na een bepaald aantal dagen verlopen of dat deze nooit verlopen.

## <a name="set-password-expiration-policy"></a>Wachtwoordverloopbeleid instellen

> [!Tip]
> Wachtwoorden verlopen standaard na 90 dagen. Recent onderzoek geeft sterk aan dat verplichte wachtwoordwijzigingen meer kwaad dan goed doen. Gebruikers kiezen dan voor zwakkere wachtwoorden, hergebruik van wachtwoorden of ze werken oude wachtwoorden bij op een manier die eenvoudig te raden is voor hackers. Als u de wachtwoorden instelt om nooit te verlopen, raden we u aan [meervoudige verificatie](../security-and-compliance/set-up-multi-factor-authentication.md) in te schakelen.

Volg onderstaande stappen als u wilt instellen dat gebruikerswachtwoorden na een bepaalde tijd verlopen.

1. Ga in het beheercentrum naar **Instellingen** \> **Organisatie-instellingen**.

2. Ga naar de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Beveiliging en privacy</a>.
 Als u geen globale beheerder bent, ziet u de optie Beveiliging en privacy niet.
  
3. Selecteer **Verloopbeleid wachtwoorden**.
  
4. Als u niet wilt dat gebruikers hun wachtwoorden moeten wijzigen, deselecteert u het selectievakje naast **Gebruikerswachtwoorden instellen om na een aantal dagen te verlopen**.
  
5. Geef op hoe vaak wachtwoorden moeten verlopen. Kies een aantal dagen tussen 14 en 730.
  
6. Geef in het tweede vak op wanneer gebruikers een melding ontvangen over het verlopen van het wachtwoord en selecteer vervolgens **Opslaan**. Kies een aantal dagen tussen 1 en 30.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>Belangrijke dingen die u moet weten over de functie voor verlopen wachtwoorden
  
- Personen die alleen gebruikmaken van de Outlook-app worden niet gedwongen hun Microsoft 365-beheerderswachtwoord opnieuw in te stellen voordat het in de cache is verlopen. Dit kan enkele dagen na de feitelijke verloopdatum in beslag nemen. Op beheerdersniveau is er geen tijdelijke oplossing voor dit probleem.

## <a name="prevent-last-password-from-being-used-again"></a>Voorkomen dat laatste wachtwoord opnieuw wordt gebruikt

Als u wilt voorkomen dat uw gebruikers oude wachtwoorden opnieuw gebruiken, kunt u dit doen door Wachtwoordgeschiedenis afdwingen in te stellen in on-premises Active Directory (AD). Raadpleeg [Een aangepast wachtwoordbeleid aanmaken](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).

In Azure AD kan het laatste wachtwoord niet opnieuw worden gebruikt als de gebruiker een wachtwoord wijzigt. Het wachtwoordbeleid wordt toegepast op alle gebruikersaccounts die rechtstreeks in Azure AD worden aangemaakt en beheerd. Dit wachtwoordbeleid kan niet worden aangepast. Raadpleeg [Azure AD-wachtwoordbeleid](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>Gebruikerswachtwoordhashes synchroniseren vanuit een on-premises Active Directory naar Azure AD (Microsoft 365) 

Dit artikel gaat over het instellen van het vervalbeleid voor gebruikers die alleen de cloud gebruiken (Azure AD). Dit geldt niet voor hybride-identiteitsgebruikers die gebruikmaken van wachtwoordhashsynchronisatie, Pass Through-verificatie of on-premises federatie, zoals ADFS.
  
Zie [Wachtwoordhashsynchronisatie met Azure AD Connect-synchronisatie implementeren](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) voor informatie over het synchroniseren van gebruikerswachtwoordhashes in een on-premises AD met gebruikerswachtwoordhashes in Azure AD.

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a>Wachtwoordbeleid en accountbeperkingen in Azure Active Directory.

U kunt meer wachtwoordbeleidsregels en beperkingen in Azure Active Directory instellen. Voor meer informatie, gaat u naar [Wachtwoordbeleid en accountbeperkingen in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy).

## <a name="update-password-policy"></a>Wachtwoordbeleid bijwerken

Met de cmdlet Set-MsolPasswordPolicy wordt het wachtwoordbeleid van een opgegeven domein of tenant bijgewerkt. Er zijn twee instellingen vereist. De eerste is om aan te geven hoe lang een wachtwoord geldig mag blijven voordat het moet worden gewijzigd en de tweede is om het aantal dagen aan te geven tot de vervaldatum van het wachtwoord, wat de eerste melding activeert die gebruikers ontvangen en hen vertelt dat het wachtwoord binnenkort vervalt.

Voor meer informatie over het bijwerken van wachtwoordbeleid voor een specifiek domein of tenant, raadpleegt u [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).

## <a name="related-content"></a>Verwante onderwerpen

[Gebruikers toestaan hun eigen wachtwoord opnieuw in te stellen](../add-users/let-users-reset-passwords.md)

[Wachtwoorden opnieuw instellen](../add-users/reset-passwords.md)