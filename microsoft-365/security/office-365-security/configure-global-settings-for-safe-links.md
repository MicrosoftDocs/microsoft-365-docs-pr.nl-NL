---
title: Algemene instellingen configureren voorinstellingen voor veilige koppelingen in Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie over het weergeven en configureren van globale instellingen (de lijst de volgende Url's blokkeren en beveiliging voor Office 365-apps) voor veilige koppelingen in Microsoft Defender voor Office 365.
ms.openlocfilehash: bc44432d4d9478e4c6a2414a70acc785c5b2c005
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682903"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Algemene instellingen configureren voor veilige koppelingen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](office-365-atp.md) hebben. Als u een thuisgebruiker bent die op zoek bent naar informatie over Safelinks in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Veilige koppelingen is een functie in [Microsoft Defender voor Office 365](office-365-atp.md) met het scannen van inkomende e-mailberichten in de e-mail stroom, en de tijd waarop u kunt klikken op verificatie van url's en koppelingen in e-mailberichten en andere locaties. Zie voor meer informatie [veilige koppelingen in Microsoft Defender voor Office 365](atp-safe-links.md).

U configureert de meeste instellingen voor veilige koppelingen in beleidsregels voor veilige koppelingen. Zie [beleid voor veilige koppelingen instellen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)voor instructies.

Voor veilige koppelingen worden ook globale instellingen gebruikt die van toepassing zijn op alle gebruikers die deel uitmaken van een actief beleid voor veilige koppelingen. Dit gebied algemene instellingen:

- De lijst **de volgende Url's blokkeren** . Zie voor meer informatie [de lijst de volgende Url's blokkeren voor veilige koppelingen](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Beveiliging van veilige koppelingen voor Office 365-apps. Zie [instellingen voor veilige koppelingen voor Office 365-apps](atp-safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.

U kunt de algemene instellingen voor veilige koppelingen in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell) configureren voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvak van Exchange Online, maar met invoegtoepassingen voor Microsoft Office 365.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- De functies van de algemene instellingen voor veilige koppelingen worden alleen toegepast op gebruikers die deel uitmaken van de beleidsregels voor actieve veilige koppelingen. Er is geen ingebouwd of standaardbeleid voor veilige koppelingen, dus u moet minimaal één beleid voor veilige koppelingen maken om deze algemene instellingen te activeren. Zie [beleid voor veilige koppelingen instellen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)voor instructies.

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina met **veilige koppelingen** wilt gaan, gebruikt u <https://protection.office.com/safelinksv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:
  - Als u de algemene instellingen voor veilige koppelingen wilt configureren, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .
  - Voor alleen-lezen toegang tot de algemene instellingen voor veilige koppelingen, moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Zie [instellingen voor veilige koppelingen](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)voor de aanbevolen waarden voor de algemene instellingen voor veilige koppelingen.

- Maximaal 30 minuten toegestaan voor het toepassen van een nieuwe of bijgewerkte beleidsregels.

- [Nieuwe functies worden continu toegevoegd aan Microsoft Defender voor Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365). Wanneer nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande beleid voor veilige koppelingen aanpassen.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>De lijst ' de volgende Url's blokkeren ' in het beveiligings & nalevings centrum configureren

De lijst **de volgende Url's blokkeren** identificeert de koppelingen die u altijd moet blokkeren door veilige koppelingen in ondersteunde apps te scannen. Zie voor meer informatie [de lijst de volgende Url's blokkeren voor veilige koppelingen](atp-safe-links.md#block-the-following-urls-list-for-safe-links).

1. Ga in het beveiligings & nalevings centrum naar veilige koppelingen voor het beleid voor **bedreigings beheer** \>  \> en klik vervolgens op **algemene instellingen**.

2. Ga in het **beleid voor veilige koppelingen voor uw organisatie** dat wordt weergegeven naar het vak **Blokkeer de volgende url's** .

3. Configureer een of meer vermeldingen zoals beschreven in [de invoer syntaxis voor de lijst ' de volgende Url's blokkeren '](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

   Wanneer u gereed bent, klikt u op **Opslaan**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>De lijst "de volgende Url's blokkeren" in PowerShell configureren

Zie de [invoer syntaxis voor de lijst ' de volgende Url's blokkeren '](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)voor meer informatie over de syntaxis van de invoer.

Met de cmdlet **Get-AtpPolicyForO365** kunt u bestaande vermeldingen in de _BlockURLs_ -eigenschap weergeven.

- Als u waarden wilt toevoegen waarmee bestaande items worden vervangen, gebruikt u de volgende syntaxis in PowerShell van Exchange Online of Exchange Online Protection:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  In het volgende voorbeeld worden de volgende items aan de lijst toegevoegd:

  - Blokkeer het domein, subdomeinen en paden voor fabrikam.com.
  - Het onderzoek subdomein blokkeren, maar niet het bovenliggende domein of andere subdomeinen in tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Gebruik de volgende syntaxis om waarden toe te voegen of te verwijderen zonder dat dit invloed heeft op andere bestaande vermeldingen:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  In dit voorbeeld wordt een nieuwe vermelding voor adatum.com toegevoegd en wordt de vermelding voor fabrikam.com verwijderd.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Beveiliging van veilige koppelingen voor Office 365-apps configureren in het beveiligings & nalevings centrum

Beveiliging van veilige koppelingen voor Office 365-apps is van toepassing op documenten in ondersteunde Office-Desktop-, mobiele en web-apps. Zie [instellingen voor veilige koppelingen voor Office 365-apps](atp-safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.

1. Ga in het beveiligings & nalevings centrum naar veilige koppelingen voor het beleid voor **bedreigings beheer** \>  \> en klik vervolgens op **algemene instellingen**.

2. In het **beleid voor veilige koppelingen voor uw organisatie** die wordt weergegeven, configureert u de volgende instellingen in de sectie **instellingen van toepassing op inhoud met uitzondering van e-mailberichten** :

   - **Office 365-toepassingen**: Controleer of de wisselknop naar rechts is ingesteld voor ondersteunde Office 365-apps: Schakel ![ over ](../../media/scc-toggle-on.png) .

   - **Niet bijhouden wanneer gebruikers op veilige koppelingen klikken**: schuif de wisselknop naar links om de gebruikers klikken met geblokkeerde url's bij te houden in ondersteunde Office 365-apps: ![ uitschakelen ](../../media/scc-toggle-off.png) .

   - **Laat gebruikers niet via veilige koppelingen naar de oorspronkelijke URL klikken**: Controleer of de wisselknop zich rechts bevindt om te voorkomen dat gebruikers door doorgaan naar de oorspronkelijke geblokkeerde URL in ondersteunde Office 365-apps: ![ Schakel over ](../../media/scc-toggle-on.png) .

   Wanneer u gereed bent, klikt u op **Opslaan**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Beveiliging van veilige koppelingen voor Office 365-apps in PowerShell configureren

Als u liever met behulp van PowerShell de bescherming van veilige koppelingen voor Office 365-Apps wilt configureren, gebruikt u de volgende syntaxis in PowerShell van Exchange Online of Exchange Online Protection:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

In dit voorbeeld worden de volgende instellingen geconfigureerd voor beveiliging van veilige koppelingen in Office 365-apps:

- Veilige koppelingen voor Office 365-apps zijn ingeschakeld (de parameter _EnableSafeLinksForO365Clients_ wordt niet gebruikt en de standaardwaarde is $True).
- De gebruiker klikt op met geblokkeerde Url's in ondersteunde Office 365-apps worden bijgehouden.
- Gebruikers mogen niet op de oorspronkelijke geblokkeerde URL klikken in ondersteunde Office 365-apps (de _AllowClickThrough_ -parameter wordt niet gebruikt en de standaardwaarde is $False).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Zie [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Voer een van de volgende stappen uit om te controleren of u de algemene instellingen voor veilige koppelingen hebt geconfigureerd (de lijst **de volgende Url's blokkeren** en de instellingen voor de beveiligingsinstellingen van Office 365-apps):

- Ga in het beveiligings & compliance naar veilige koppelingen voor het beleid voor **risicobeheer** \>  \> , klik op **algemene instellingen** en controleer de instellingen in het venster dat wordt weergegeven.

- Voer de volgende opdracht uit in PowerShell van Exchange Online of Exchange Online Protection en controleer de instellingen:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Zie [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.
