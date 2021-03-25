---
title: Algemene instellingen configureren voor instellingen voor veilige koppelingen in Defender voor Office 365
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
description: Beheerders kunnen meer informatie krijgen over het weergeven en configureren van algemene instellingen (de lijst 'De volgende URL's blokkeren' en beveiliging voor Office 365-apps) voor Veilige koppelingen in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 390177a24648cf860a78ab831d5dfe334b2c9590
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203936"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Algemene instellingen configureren voor veilige koppelingen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](defender-for-office-365.md) hebben. Als u een thuisgebruiker bent die informatie zoekt over Safelinks in Outlook, bekijkt u [Geavanceerde Outlook.com beveiliging.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Veilige koppelingen is een functie in Microsoft Defender voor [Office 365](defender-for-office-365.md) waarmee url's worden gescand van binnenkomende e-mailberichten in de e-mailstroom en het tijdstip van klikverificatie van URL's en koppelingen in e-mailberichten en op andere locaties. Zie Veilige koppelingen [in Microsoft Defender voor Office 365](safe-links.md)voor meer informatie.

U configureert de meeste instellingen voor veilige koppelingen in beleidsregels voor veilige koppelingen. Zie Beleidsregels voor veilige koppelingen instellen [in Microsoft Defender voor Office 365](set-up-safe-links-policies.md)voor instructies.

Veilige koppelingen maken echter ook gebruik van globale instellingen die van toepassing zijn op alle gebruikers die zijn opgenomen in een actief beleid voor veilige koppelingen. Dit gebied met globale instellingen:

- De **lijst De volgende URL's** blokkeren. Zie De volgende URL's blokkeren voor veilige koppelingen voor [meer informatie.](safe-links.md#block-the-following-urls-list-for-safe-links)
- Beveiliging van veilige koppelingen voor Office 365-apps. Zie Instellingen voor veilige koppelingen voor [Office 365-apps](safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.

U kunt de algemene instellingen voor veilige koppelingen configureren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Microsoft Defender voor Office 365-invoegabonnementen).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- De functies van globale instellingen voor veilige koppelingen worden alleen toegepast op gebruikers die zijn opgenomen in actief beleid voor veilige koppelingen. Er is geen ingebouwd of standaardbeleid voor veilige koppelingen, dus u moet ten minste één beleid voor veilige koppelingen maken om ervoor te zorgen dat deze globale instellingen actief zijn. Zie Beleidsregels voor veilige koppelingen instellen [in Microsoft Defender voor Office 365](set-up-safe-links-policies.md)voor instructies.

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Veilige koppelingen wilt** gaan, gebruikt u <https://protection.office.com/safelinksv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u de algemene instellingen voor veilige koppelingen wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Als u alleen-lezen toegang wilt tot de algemene instellingen voor  veilige koppelingen, moet u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Zie Instellingen voor veilige koppelingen voor onze aanbevolen waarden voor de algemene instellingen voor [veilige koppelingen.](recommended-settings-for-eop-and-office365.md#safe-links-settings)

- Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.

- [Er worden voortdurend nieuwe functies toegevoegd aan Microsoft Defender voor Office 365.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365) Als er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande beleid voor veilige koppelingen aanpassen.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>De lijst 'De volgende URL's blokkeren' configureren in het beveiligings- & compliancecentrum

In **de lijst De volgende URL's** blokkeren worden de koppelingen geïdentificeerd die altijd moeten worden geblokkeerd door het scannen van veilige koppelingen in ondersteunde apps. Zie De volgende URL's blokkeren voor veilige koppelingen voor [meer informatie.](safe-links.md#block-the-following-urls-list-for-safe-links)

1. Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP-veilige koppelingen** en klik vervolgens op Algemene **instellingen.**

2. In het **beleid voor veilige koppelingen voor uw organisatie** dat wordt weergegeven, gaat u naar het vak De volgende **URL's blokkeren.**

3. Configureer een of meer vermeldingen zoals beschreven in [de syntaxis van entry voor de lijst 'De volgende URL's blokkeren'.](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Klik op **Opslaan** wanneer u gereed bent.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>De lijst 'De volgende URL's blokkeren' configureren in PowerShell

Zie De syntaxis van invoer voor de lijst ['De volgende URL's blokkeren'](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)voor meer informatie over de syntaxis van het item.

U kunt de **cmdlet Get-AtpPolicyForO365** gebruiken om bestaande items in de eigenschap _BlockURLs te_ bekijken.

- Als u waarden wilt toevoegen die bestaande vermeldingen vervangen, gebruikt u de volgende syntaxis in Exchange Online PowerShell of Exchange Online Protection PowerShell:

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

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Beveiliging van veilige koppelingen configureren voor Office 365-apps in & Beveiligingscentrum

Beveiliging van veilige koppelingen voor Office 365-apps is van toepassing op documenten in ondersteunde Office-bureaublad-, mobiele en web-apps. Zie Instellingen voor veilige koppelingen voor [Office 365-apps](safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.

1. Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP-veilige koppelingen** en klik vervolgens op Algemene **instellingen.**

2. In het **beleid voor veilige** koppelingen voor uw organisatie dat wordt weergegeven, configureert u de volgende instellingen in de sectie Instellingen die van toepassing zijn op **inhoud, behalve e-mail:**

   - **Office 365-toepassingen:** Controleer of de schakelknop rechts is om Veilige koppelingen in te schakelen voor ondersteunde Office 365-apps: ![ Schakel ](../../media/scc-toggle-on.png) in.

   - **Houd niet bij wanneer** gebruikers op Veilige koppelingen klikken: Verplaats de schakelknop naar links om klikken van gebruikers met betrekking tot geblokkeerde URL's in ondersteunde Office 365-apps bij te houden: Schakel de schakelknop ![ ](../../media/scc-toggle-off.png) uit.

   - **Laat gebruikers** niet door veilige koppelingen naar de oorspronkelijke URL klikken: controleer of de schakelknop rechts is om te voorkomen dat gebruikers doorklikken naar de oorspronkelijke geblokkeerde URL in ondersteunde Office 365-apps: ![ Schakel ](../../media/scc-toggle-on.png) in.

   Klik op **Opslaan** wanneer u gereed bent.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Beveiliging voor veilige koppelingen configureren voor Office 365-apps in PowerShell

Als u Liever PowerShell gebruikt om beveiliging voor veilige koppelingen voor Office 365-apps te configureren, gebruikt u de volgende syntaxis in Exchange Online PowerShell of Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

In dit voorbeeld worden de volgende instellingen geconfigureerd voor beveiliging van veilige koppelingen in Office 365-apps:

- Veilige koppelingen voor Office 365-apps is ingeschakeld (we gebruiken de parameter _EnableSafeLinksForO365Clients_ niet en de standaardwaarde is $true).
- Gebruikersklikken met betrekking tot geblokkeerde URL's in ondersteunde Office 365-apps worden bijgehouden.
- Gebruikers mogen niet doorklikken naar de oorspronkelijke geblokkeerde URL in ondersteunde Office 365-apps (we gebruiken de parameter _AllowClickThrough_ niet en de standaardwaarde is $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Zie [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga als volgt te werk om te controleren of u de algemene instellingen voor veilige koppelingen hebt geconfigureerd (de lijst De volgende **URL's** blokkeren en de instellingen voor app-beveiliging van Office 365) hebt geconfigureerd:

- Ga in & Beveiligingscentrum naar Beveiligingsbeheerbeleid  ATP-veilige koppelingen , klik op Algemene instellingen en controleer de instellingen in de \>  \> fly-out die wordt weergegeven. 

- Voer in Exchange Online PowerShell of Exchange Online Protection PowerShell de volgende opdracht uit en controleer de instellingen:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Zie [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis- en parametergegevens.