---
title: Algemene instellingen configureren voorinstellingen voor veilige koppelingen in Office 365 ATP
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
description: Beheerders kunnen informatie over het weergeven en configureren van globale instellingen (de lijst de volgende Url's blokkeren en beveiliging voor Office 365-apps) voor veilige koppelingen in Office 365 Advanced Threat Protection (ATP).
ms.openlocfilehash: 50bef8a1edad50540c7212eb4259e17e2368a56c
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350875"
---
# <a name="configure-global-settings-for-safe-links-in-office-365-atp"></a>Algemene instellingen voor veilige koppelingen in Office 365 ATP configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Als u een thuisgebruiker bent die op zoek bent naar informatie over Safelinks in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Veilige koppelingen is een functie in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) voor het scannen van inkomende e-mailberichten in de e-mail stroom, en de tijd van de verificatie van url's en koppelingen in e-mailberichten en op andere locaties. Zie voor meer informatie [veilige koppelingen in Office 365 ATP](atp-safe-links.md).

U configureert de meeste instellingen voor veilige koppelingen in beleidsregels voor veilige koppelingen. Zie [beleid voor veilige koppelingen instellen in Office 365 ATP](set-up-atp-safe-links-policies.md)voor instructies.

Voor veilige koppelingen worden ook globale instellingen gebruikt die van toepassing zijn op alle gebruikers die deel uitmaken van een actief beleid voor veilige koppelingen. Dit gebied algemene instellingen:

- De lijst **de volgende Url's blokkeren** . Zie voor meer informatie [de lijst de volgende Url's blokkeren voor veilige koppelingen](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Beveiliging van veilige koppelingen voor Office 365-apps. Zie [instellingen voor veilige koppelingen voor Office 365-apps](atp-safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.

U kunt de algemene instellingen voor veilige koppelingen in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell) configureren voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Office 365.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- De functies van de algemene instellingen voor veilige koppelingen worden alleen toegepast op gebruikers die deel uitmaken van de beleidsregels voor actieve veilige koppelingen. Er is geen ingebouwd of standaardbeleid voor veilige koppelingen, dus u moet minimaal één beleid voor veilige koppelingen maken om deze algemene instellingen te activeren. Zie [beleid voor veilige koppelingen instellen in Office 365 ATP](set-up-atp-safe-links-policies.md)voor instructies.

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u direct naar de pagina voor **veilige koppelingen voor ATP** wilt gaan, gebruikt u <https://protection.office.com/safelinksv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- Als u de algemene instellingen voor veilige koppelingen wilt weergeven en configureren, moet u lid zijn van een van de volgende groepen rollen:

  - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
  - **Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Zie [instellingen voor veilige koppelingen](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)voor de aanbevolen waarden voor de algemene instellingen voor veilige koppelingen.

- Maximaal 30 minuten toegestaan voor het toepassen van een nieuwe of bijgewerkte beleidsregels.

- [Nieuwe functies worden continu toegevoegd aan ATP](office-365-atp.md#new-features-in-office-365-atp). Wanneer nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande beleid voor veilige koppelingen aanpassen.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>De lijst ' de volgende Url's blokkeren ' in het beveiligings & nalevings centrum configureren

De lijst **de volgende Url's blokkeren** identificeert de koppelingen die u altijd moet blokkeren door veilige koppelingen in ondersteunde apps te scannen. Zie voor meer informatie [de lijst de volgende Url's blokkeren voor veilige koppelingen](atp-safe-links.md#block-the-following-urls-list-for-safe-links).

1. Ga in het beveiligings & nalevings centrum naar veilige koppelingen voor het beleid voor **bedreigings beheer** \> **Policy** \> **ATP Safe Links**en klik vervolgens op **algemene instellingen**.

2. Ga in het **beleid voor veilige koppelingen voor uw organisatie** dat wordt weergegeven naar het vak **Blokkeer de volgende url's** .

3. Configureer een of meer vermeldingen zoals beschreven in [de invoer syntaxis voor de lijst ' de volgende Url's blokkeren '](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

   Klik op **Opslaan** wanneer u gereed bent.

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

1. Ga in het beveiligings & nalevings centrum naar veilige koppelingen voor het beleid voor **bedreigings beheer** \> **Policy** \> **ATP Safe Links**en klik vervolgens op **algemene instellingen**.

2. In het **beleid voor veilige koppelingen voor uw organisatie** die wordt weergegeven, configureert u de volgende instellingen in de sectie **instellingen van toepassing op inhoud met uitzondering van e-mailberichten** :

   - **Office 365-toepassingen**: Controleer of de wisselknop naar rechts is ingesteld voor ondersteunde Office 365-apps: Schakel ![ over ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   - **Niet bijhouden wanneer gebruikers op veilige koppelingen klikken**: schuif de wisselknop naar links om de gebruikers klikken met geblokkeerde url's bij te houden in ondersteunde Office 365-apps: ![ uitschakelen ](../../media/scc-toggle-off.png) .

   - **Laat gebruikers niet via veilige koppelingen naar de oorspronkelijke URL klikken**: Controleer of de wisselknop zich rechts bevindt om te voorkomen dat gebruikers door doorgaan naar de oorspronkelijke geblokkeerde URL in ondersteunde Office 365-apps: ![ Schakel over ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   Klik op **Opslaan** wanneer u gereed bent.

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

- Ga in het beveiligings & compliance naar veilige koppelingen voor het beleid voor **risicobeheer** \> **Policy** \> **ATP Safe Links**, klik op **algemene instellingen**en controleer de instellingen in het venster dat wordt weergegeven.

- Voer de volgende opdracht uit in PowerShell van Exchange Online of Exchange Online Protection en controleer de instellingen:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Zie [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)voor gedetailleerde syntaxis-en parameterinformatie.
