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
description: Beheerders kunnen meer informatie krijgen over het weergeven en configureren van globale instellingen (de lijst 'De volgende URL's blokkeren' en beveiliging voor Office 365-apps) voor veilige koppelingen in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 885fe6a06cce054bea6d6f20c24c5c1f2a159c07
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165725"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Algemene instellingen configureren voor veilige koppelingen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](office-365-atp.md) hebben. Als u een thuisgebruiker bent en op zoek bent naar informatie over Safelinks in Outlook, gaat u naar [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Veilige koppelingen is een functie in Microsoft Defender voor [Office 365](office-365-atp.md) waarmee de URL wordt gescand van binnenkomende e-mailberichten in de e-mailstroom en het tijdstip van klikverificatie van URL's en koppelingen in e-mailberichten en op andere locaties. Zie Veilige koppelingen [in Microsoft Defender voor Office 365](atp-safe-links.md)voor meer informatie.

U configureert de meeste instellingen voor veilige koppelingen in het beleid voor veilige koppelingen. Zie Beleidsregels voor veilige [koppelingen instellen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)voor instructies.

Veilige koppelingen maken echter ook gebruik van globale instellingen die van toepassing zijn op alle gebruikers die zijn opgenomen in een actief beleid voor veilige koppelingen. Dit gebied met globale instellingen:

- De **lijst met de volgende URL's** blokkeren. Zie de lijst ['De volgende URL's blokkeren'](atp-safe-links.md#block-the-following-urls-list-for-safe-links) voor meer informatie over veilige koppelingen
- Beveiliging tegen veilige koppelingen voor Office 365-apps. Zie instellingen voor veilige koppelingen [voor Office 365-apps](atp-safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.

U kunt de globale instellingen voor veilige koppelingen configureren in het beveiligings- &-compliancecentrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Microsoft Defender voor Office 365-invoegabonnementen).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- De functies die worden geboden door globale instellingen voor veilige koppelingen, worden alleen toegepast op gebruikers die zijn opgenomen in het actieve beleid voor veilige koppelingen. Er is geen ingebouwd of standaardbeleid voor veilige koppelingen. U moet dus ten minste één beleid voor veilige koppelingen maken om deze globale instellingen actief te maken. Zie Beleidsregels voor veilige [koppelingen instellen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)voor instructies.

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Veilige koppelingen wilt** gaan, gebruikt u <https://protection.office.com/safelinksv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:
  - Als u de algemene instellingen voor veilige koppelingen wilt configureren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Voor alleen-lezen toegang tot de globale instellingen voor veilige koppelingen  moet u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Zie instellingen voor veilige koppelingen voor de aanbevolen waarden voor de globale instellingen [voor veilige koppelingen.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)

- Het kan 30 minuten duren voordat een nieuw of bijgewerkt beleid wordt toegepast.

- [Nieuwe functies worden voortdurend toegevoegd aan Microsoft Defender voor Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365) Naarmate er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande beleidsregels voor veilige koppelingen aanpassen.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>De lijst 'De volgende URL's blokkeren' configureren in het & compliancecentrum

In **de lijst Met de volgende URL's** blokkeren worden de koppelingen geïdentificeerd die altijd moeten worden geblokkeerd door het scannen van veilige koppelingen in ondersteunde apps. Zie de lijst ['De volgende URL's blokkeren' voor meer](atp-safe-links.md#block-the-following-urls-list-for-safe-links)informatie over veilige koppelingen.

1. Ga in het & compliancecentrum naar  Veilige koppelingen van ATP voor bedreigingsbeheerbeleid en klik op \>  \>  **Globale instellingen.**

2. In het **beleid voor veilige koppelingen voor uw** organisatie dat wordt weergegeven, gaat u naar het vak De volgende **URL's blokkeren.**

3. Configureer een of meer vermeldingen zoals wordt beschreven in de syntaxis voor invoer voor de lijst 'De volgende [URL's blokkeren'.](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Klik op **Opslaan** wanneer u gereed bent.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>De lijst 'De volgende URL's blokkeren' configureren in PowerShell

Zie de syntaxis voor invoer voor de lijst 'De volgende [URL's blokkeren'](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)voor meer informatie over de syntaxis van de invoer.

U kunt de cmdlet **Get-AtpPolicyForO365** gebruiken om bestaande vermeldingen in de eigenschap _BlockURLs te_ bekijken.

- Als u waarden wilt toevoegen die eventuele bestaande items vervangen, gebruikt u de volgende syntaxis in Exchange Online PowerShell of Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  In dit voorbeeld worden de volgende items toegevoegd aan de lijst:

  - Blokkeer het domein, subdomeinen en paden voor fabrikam.com.
  - Het subdomeinonderzoek blokkeren, maar niet het bovenliggende domein of andere subdomeinen in tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Gebruik de volgende syntaxis om waarden toe te voegen of te verwijderen zonder dat dit van invloed is op andere bestaande gegevens:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  In dit voorbeeld wordt een nieuw item voor adatum.com toegevoegd en wordt de vermelding voor fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Beveiliging van veilige koppelingen configureren voor Office 365-apps in het & compliancecentrum

Beveiliging tegen veilige koppelingen voor Office 365-apps is van toepassing op documenten in ondersteunde Office-bureaublad-, mobiele en web-apps. Zie instellingen voor veilige koppelingen [voor Office 365-apps](atp-safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.

1. Ga in het & compliancecentrum naar  Veilige koppelingen van ATP voor bedreigingsbeheerbeleid en klik op \>  \>  **Globale instellingen.**

2. In het **beleid voor veilige koppelingen voor uw** organisatie dat wordt weergegeven, configureert u de volgende instellingen in de instellingen die van toepassing zijn op inhoud behalve **e-mailsectie:**

   - **Office 365-toepassingen:** controleer of de schakelknop aan de rechterkant staat om Veilige koppelingen in te schakelen voor ondersteunde Office 365-apps: ![ In-/uitschakelen. ](../../media/scc-toggle-on.png)

   - **Houd niet bij** wanneer gebruikers op Veilige koppelingen klikken: zet de schakelaar naar links om klikken van gebruikers met betrekking tot geblokkeerde URL's in ondersteunde Office 365-apps bij te ![ houden: In-/uitschakelen. ](../../media/scc-toggle-off.png)

   - Laat gebruikers niet doorklikken naar de oorspronkelijke **URL:** controleer of de schakelknop aan de rechterkant is om te voorkomen dat gebruikers doorklikken naar de oorspronkelijke, geblokkeerde URL in ondersteunde Office 365-apps: In-/uitschakelen. ![ ](../../media/scc-toggle-on.png)

   Klik op **Opslaan** wanneer u gereed bent.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Beveiliging van veilige koppelingen configureren voor Office 365-apps in PowerShell

Als u liever PowerShell gebruikt om beveiliging tegen veilige koppelingen voor Office 365-apps te configureren, gebruikt u de volgende syntaxis in Exchange Online PowerShell of Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

In dit voorbeeld worden de volgende instellingen geconfigureerd voor beveiliging tegen veilige koppelingen in Office 365-apps:

- Veilige koppelingen voor Office 365-apps is ingeschakeld (we gebruiken niet de parameter _EnableSafeLinksForO365Clients_ en de standaardwaarde is $true).
- Klikken van gebruikers met betrekking tot geblokkeerde URL's in ondersteunde Office 365-apps worden bijgehouden.
- Gebruikers kunnen niet doorklikken naar de oorspronkelijke, geblokkeerde URL in ondersteunde Office 365-apps (we gebruiken de parameter _AllowClickThrough_ niet en de standaardwaarde is $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Zie [Set-AtpPolicyForO365 voor](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u de globale instellingen voor veilige koppelingen hebt geconfigureerd (de lijst met de volgende **URL's** en de beveiligingsinstellingen voor Office 365-apps blokkeren), gaat u op een van de volgende stappen te werk:

- Ga in het & compliancecentrum naar  Veilige koppelingen van ATP voor risicobeheerbeleid, klik op Globale instellingen en controleer de instellingen in de \>  \> fly out die wordt weergegeven. 

- Voer in Exchange Online PowerShell of Exchange Online Protection PowerShell de volgende opdracht uit en controleer de instellingen:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Zie [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis- en parameterinformatie.
