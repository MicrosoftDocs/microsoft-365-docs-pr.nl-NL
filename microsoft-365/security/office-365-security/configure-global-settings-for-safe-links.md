---
title: Algemene instellingen configureren voor Safe koppelingen in Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over het weergeven en configureren van algemene instellingen (de lijst 'De volgende URL's blokkeren' en beveiliging voor Office 365-apps) voor Safe-koppelingen in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 623b1bcd670f42c7c6b49c06cacfa31cb8adfd49
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/07/2021
ms.locfileid: "52792990"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Algemene instellingen configureren voor Safe koppelingen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](defender-for-office-365.md) hebben. Als u een thuisgebruiker bent die informatie zoekt over Safelinks in Outlook, gaat u naar [Advanced Outlook.com-beveiliging.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Safe Koppelingen is een functie in [Microsoft Defender voor Office 365](defender-for-office-365.md) waarmee url's worden gescand van binnenkomende e-mailberichten in de e-mailstroom en de tijd van klikverificatie van URL's en koppelingen in e-mailberichten en op andere locaties. Zie Koppelingen in Microsoft Defender voor Safe voor [meer Office 365.](safe-links.md)

U configureert de Safe koppelingen in Safe koppelingenbeleid. Zie Beleidsregels voor [koppelingen instellen Safe Microsoft Defender voor](set-up-safe-links-policies.md)Office 365.

Voor Safe koppelingen worden echter ook de volgende algemene instellingen gebruikt die u buiten het beleid Safe Koppelingen zelf configureert:

- De **lijst De volgende URL's** blokkeren. Deze instelling is van toepassing op alle gebruikers die zijn opgenomen in een actief Safe Koppelingenbeleid. Zie 'De volgende [URL's blokkeren'](safe-links.md#block-the-following-urls-list-for-safe-links) voor meer Safe Koppelingen
- Safe Koppelingenbeveiliging voor Office 365 apps. Deze instellingen zijn van toepassing op alle gebruikers in de organisatie die een licentie hebben voor Defender voor Office 365, ongeacht of de gebruikers zijn opgenomen in het beleid voor actieve Safe Koppelingen of niet. Zie de instellingen voor koppelingen Safe voor Office 365 [voor meer informatie.](safe-links.md#safe-links-settings-for-office-365-apps)

U kunt de instellingen voor globale Safe-koppelingen configureren in het Microsoft 365-beveiligingscentrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Microsoft Defender voor Office 365-invoegabonnementen).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Er is geen ingebouwd Safe standaardbeleid voor koppelingen, dus u moet ten minste één Safe-koppelingenbeleid maken om ervoor te zorgen dat de lijst Met de volgende **URL's** blokkeren actief is. Zie Beleidsregels voor [koppelingen instellen Safe Microsoft Defender voor](set-up-safe-links-policies.md)Office 365.

- U opent het beveiligingscentrum in <https://security.microsoft.com/>. Als u rechtstreeks naar de pagina Safe **koppelingen wilt** gaan, gebruikt <https://security.microsoft.com/safelinksv2> u .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u de algemene instellingen voor Safe koppelingen wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot de algemene instellingen voor Safe koppelingen,  moet u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Zie voor onze aanbevolen waarden voor de algemene instellingen voor Safe Koppelingen [Safe Koppelingen.](recommended-settings-for-eop-and-office365.md#safe-links-settings)

- Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.

- [Er worden voortdurend nieuwe functies toegevoegd aan Microsoft Defender voor Office 365.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365) Als er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande Safe koppelingenbeleid aanpassen.

## <a name="configure-the-block-the-following-urls-list-in-the-security-center"></a>De lijst 'De volgende URL's blokkeren' configureren in het beveiligingscentrum

In **de lijst De volgende URL's** blokkeren worden de koppelingen geïdentificeerd die altijd moeten worden geblokkeerd door Safe Koppelingen scannen in ondersteunde apps. Zie 'De volgende [URL's blokkeren'](safe-links.md#block-the-following-urls-list-for-safe-links)voor meer Safe koppelingen.

1. Ga in het beveiligingscentrum naar de sectie Beleidsregels voor **e-mail & samenwerkingsbeleid** & Beleidsregels voor bedreigingsregels \>  \>  \>  \> **Safe Koppelingen.**

2. Klik op **Safe pagina Koppelingen** op Algemene **instellingen.** Ga in **Safe beleid voor koppelingen** voor uw organisatie dat wordt weergegeven naar het vak De volgende **URL's blokkeren.**

3. Configureer een of meer vermeldingen zoals beschreven in [de syntaxis van entry voor de lijst 'De volgende URL's blokkeren'.](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Klik op **Opslaan** wanneer u gereed bent.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>De lijst 'De volgende URL's blokkeren' configureren in PowerShell

Zie De syntaxis van invoer voor de lijst ['De volgende URL's blokkeren'](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)voor meer informatie over de syntaxis van het item.

U kunt de **cmdlet Get-AtpPolicyForO365** gebruiken om bestaande items in de eigenschap _BlockURLs te_ bekijken.

- Als u waarden wilt toevoegen die bestaande vermeldingen vervangen, gebruikt u de volgende syntaxis in PowerShell Exchange Online PowerShell of Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  In dit voorbeeld worden de volgende vermeldingen toegevoegd aan de lijst:

  - Blokkeer het domein, subdomeinen en paden voor fabrikam.com.
  - Het subdomeinonderzoek blokkeren, maar niet het bovenliggende domein of andere subdomeinen in tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Als u waarden wilt toevoegen of verwijderen zonder dat dit van invloed is op andere bestaande vermeldingen, gebruikt u de volgende syntaxis:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  In dit voorbeeld wordt een nieuw item voor adatum.com toegevoegd en wordt de vermelding voor fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security-center"></a>Beveiliging Safe koppelingen configureren voor Office 365 apps in het beveiligingscentrum

Safe Koppelingenbeveiliging voor Office 365 apps is van toepassing op documenten in ondersteunde Office desktop-, mobiele en web-apps. Zie de instellingen voor koppelingen Safe voor Office 365 [voor meer informatie.](safe-links.md#safe-links-settings-for-office-365-apps)

1. Ga in het beveiligingscentrum naar de sectie Beleidsregels voor **e-mail & samenwerkingsbeleid** & Beleidsregels voor bedreigingsregels \>  \>  \>  \> **Safe Koppelingen.**

2. Klik op **Safe pagina Koppelingen** op Algemene **instellingen.** In het **Safe koppelingenbeleid** voor uw organisatie dat wordt weergegeven, configureert u de volgende instellingen in de Instellingen die van toepassing zijn op inhoud in de sectie **ondersteunde Office 365 apps:**

   - **Gebruik Safe Koppelingen in Office 365 apps:** Controleer of de schakelknop rechts is om Safe Koppelingen in te schakelen voor ondersteunde Office 365 apps: ![ ](../../media/scc-toggle-on.png) Inschakelen.

   - Houd niet bij wanneer gebruikers klikken op beveiligde **koppelingen in Office 365-apps:** Verplaats de schakelknop naar links om klikken van gebruikers met betrekking tot geblokkeerde URL's in ondersteunde Office 365-apps bij te houden: ![ ](../../media/scc-toggle-off.png) Uitschakelen.

   - Laat gebruikers niet doorklikken naar de oorspronkelijke **URL in Office 365-apps:** Controleer of de schakelknop rechts is om te voorkomen dat gebruikers doorklikken naar de oorspronkelijke geblokkeerde URL in ondersteunde Office 365-apps: Schakel ![ ](../../media/scc-toggle-on.png) in.

   Klik op **Opslaan** wanneer u gereed bent.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Beveiliging Safe koppelingen configureren voor Office 365 apps in PowerShell

Als u Liever PowerShell gebruikt om Safe koppelingen te configureren voor Office 365-apps, gebruikt u de volgende syntaxis in powershell Exchange Online PowerShell Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

In dit voorbeeld worden de volgende instellingen geconfigureerd voor Safe koppelingenbeveiliging in Office 365 apps:

- Safe Koppelingen voor Office 365 apps is ingeschakeld (we gebruiken de parameter _EnableSafeLinksForO365Clients_ niet en de standaardwaarde is $true).
- Gebruikersklikken die betrekking hebben op geblokkeerde URL's in ondersteunde Office 365 apps worden bijgehouden.
- Gebruikers mogen niet doorklikken naar de oorspronkelijke geblokkeerde URL in ondersteunde Office 365-apps (we gebruiken de parameter _AllowClickThrough_ niet en de standaardwaarde is $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Zie [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga als volgt te werk om te controleren of u de algemene instellingen voor Safe-koppelingen hebt geconfigureerd (de lijst Met de volgende **URL's** blokkeren en de instellingen voor Office 365-app-beveiliging:

- Ga in het beveiligingscentrum naar Het beleid voor samenwerking & E-mail  & Beleidsregels Bedreigingsbeleid Safe Koppelingen klik op Algemene instellingen en controleer de instellingen in de \>  \>  \>  \>  \> fly-out die wordt weergegeven.

- Voer in Exchange Online PowerShell of Exchange Online Protection PowerShell de volgende opdracht uit en controleer de instellingen:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Zie [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.
