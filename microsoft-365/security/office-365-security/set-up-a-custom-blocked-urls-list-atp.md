---
title: Een aangepaste lijst met geblokkeerde URL's instellen met ATP-veilige koppelingen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het instellen van een lijst met geblokkeerde URL's voor uw organisatie met Behulp van Geavanceerde bedreigingsbeveiliging van Office 365.
ms.openlocfilehash: 9bf4417044dab5488e2945ccea5fa30a7fd4113d
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588142"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a>Een aangepaste lijst met geblokkeerde URL's instellen met ATP-veilige koppelingen

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Zie [Geavanceerde Outlook.com beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige koppelingen.

Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie een aangepaste lijst hebben met geblokkeerde websiteadressen (URL's). Wanneer een URL wordt geblokkeerd, worden mensen die op koppelingen naar de geblokkeerde URL klikken, naar een [waarschuwingspagina](atp-safe-links-warning-pages.md) geleid die lijkt op de volgende afbeelding:

![Deze site is geblokkeerd](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

De lijst met geblokkeerde URL's wordt gedefinieerd door het Microsoft 365 for Business Security-team van uw organisatie en die lijst is van toepassing op iedereen in de organisatie die onder het beleid van Office 365 ATP Safe Links valt.

Lees dit artikel voor meer informatie over het instellen van de aangepaste lijst met geblokkeerde URL's van uw organisatie voor [ATP-veilige koppelingen in Office 365](atp-safe-links.md).

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>Een aangepaste lijst met geblokkeerde URL's weergeven of bewerken

[ATP Safe Links in Office 365](atp-safe-links.md) gebruikt verschillende lijsten, waaronder de aangepaste lijst met geblokkeerde URL's van uw organisatie. Als u over de benodigde machtigingen beschikt, u de aangepaste lijst van uw organisatie instellen. U doet dit door het standaard beleid voor veilige koppelingen van uw organisatie te bewerken.

Als u ATP-beleid wilt bewerken (of definiëren), moet u een van de rollen toegewezen krijgen die in de volgende tabel worden beschreven:

|Rol|Waar/hoe toegewezen|
|---------|---------|
|globale beheerder|De persoon die zich aanmeldt om Microsoft 365 te kopen, is standaard een globale beheerder. (Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)|
|Beveiligingsbeheerder|Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Exchange Online Organisatiebeheer|Exchange-beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

> [!TIP]
> Zie [Machtigingen in het Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>Een aangepaste lijst met geblokkeerde URL's weergeven of bewerken

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je werk- of schoolaccount.

2. Kies in de linkernavigatie onder **Bedreigingsbeheer** **De optie Veilige** \> **koppelingen voor**beleid .

3. Selecteer **Policies that apply to the entire organization** **standaard**en kies **Vervolgens Bewerken** (de knop Bewerken lijkt op een potlood).<br/>![Klik op Bewerken om uw standaardbeleid voor beveiliging van veilige koppelingen te bewerken](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>Hiermee u uw lijst met geblokkeerde URL's bekijken. In eerste instantie zijn hier mogelijk geen URL's vermeld.<br/>![Lijst met geblokkeerde URL's in het standaardbeleid Veilige koppelingen](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)

4. Selecteer het vak **Een geldige URL invoeren,** typ een URL en kies het plusteken ( **+** ).

5. Wanneer u klaar bent met het toevoegen van URL's, kiest u in de rechterbenedenhoek van het scherm **Opslaan**.

## <a name="a-few-things-to-keep-in-mind"></a>Een paar dingen om in gedachten te houden

Houd rekening met de volgende punten terwijl u URL's aan uw lijst toevoegt:

- Voeg geen slash **/** (vooruit) toe aan het einde van de URL. Voer bijvoorbeeld in plaats van in te voeren `https://www.contoso.com/` `https://www.contoso.com` .

- U een url alleen voor het domein opgeven (like `contoso.com` of `tailspintoys.com` ). Hiermee worden klikken op elke URL die het domein bevat, geblokkeerd.

- U een subdomein (zoals) opgeven `toys.contoso.com*` zonder een volledig domein (zoals) te `contoso.com` blokkeren. Hiermee worden klikken op een URL die het subdomein bevat, geblokkeerd, maar wordt klikken niet geblokkeerd naar een URL die het volledige domein bevat.

- U maximaal drie wildcard sterretjes ( \* ) per URL. In de volgende tabel worden enkele voorbeelden weergegeven van wat u invoeren en welk effect deze vermeldingen hebben.

|Voorbeeldvermelding|Wat het doet|
|:-----|:-----|
|`contoso.com`Of`*contoso.com*`|Blokkeert het domein, subdomeinen en paden, zoals `https://www.contoso.com` `https://sub.contoso.com` ,`https://contoso.com/abc`|
|`https://contoso.com/a`|Blokkeert een `https://contoso.com/a` site, maar geen extra subpaden zoals`https://contoso.com/a/b`|
|`https://contoso.com/a*`|Blokkeert een site `https://contoso.com/a` en extra subpaden zoals`https://contoso.com/a/b`|
|`https://toys.contoso.com*`|Blokkeert een subdomein ("speelgoed" in dit geval), maar laat klikken naar andere domein-URL's (zoals `https://contoso.com` of `https://home.contoso.com` ).|

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>Uitzonderingen definiëren voor bepaalde gebruikers in een organisatie

Als u wilt dat bepaalde groepen URL's kunnen bekijken die mogelijk voor anderen zijn geblokkeerd, u een ATP-beleid voor veilige koppelingen opgeven dat van toepassing is op specifieke ontvangers. Zie [Een aangepaste url's-lijst 'niet herschrijven' instellen met ATP-veilige koppelingen](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
