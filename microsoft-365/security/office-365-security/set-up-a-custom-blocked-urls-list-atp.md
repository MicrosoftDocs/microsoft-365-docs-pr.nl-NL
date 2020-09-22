---
title: Een aangepaste lijst met geblokkeerde Url's met behulp van behulp van vrije verbindingen instellen
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
description: Meer informatie over het instellen van een lijst met geblokkeerde Url's voor uw organisatie met behulp van Office 365 Advanced Threat Protection.
ms.openlocfilehash: e153d5631c12d52564643477216b777cdbc49433
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201001"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a>Een aangepaste lijst met geblokkeerde Url's met behulp van behulp van vrije verbindingen instellen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Als u een thuisgebruiker bent die op zoek bent naar informatie over veilige koppelingen in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie een aangepaste lijst met websites adressen (url's) hebben die zijn geblokkeerd. Wanneer een URL is geblokkeerd, worden personen die op de koppeling naar de geblokkeerde URL klikken een [waarschuwingspagina](atp-safe-links-warning-pages.md) weergegeven die lijkt op de volgende afbeelding:

![Deze site is geblokkeerd](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

De lijst met geblokkeerde Url's wordt gedefinieerd door het beveiligingsteam van Microsoft 365 voor bedrijven en de lijst is bedoeld voor iedereen in de organisatie die wordt bedekt met beleidsregels voor veilige koppelingen in Office 365.

Lees dit artikel voor meer informatie over het instellen van de lijst met geblokkeerde Url's van uw organisatie voor veilige weergave-instellingen [in Office 365](atp-safe-links.md).

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>Een aangepaste lijst met geblokkeerde Url's weergeven of bewerken

[Voor veilige koppelingen in Office 365](atp-safe-links.md) worden verschillende lijsten gebruikt, waaronder de aangepaste lijst met geblokkeerde url's van uw organisatie. Als u de benodigde machtigingen hebt, kunt u de aangepaste lijst van uw organisatie instellen. Dit doet u door het standaardbeleid voor veilige koppelingen van uw organisatie te bewerken.

Als u een ATP-beleid wilt bewerken (of definiëren), moet u een van de rollen krijgen die in de volgende tabel worden beschreven:

****

|Rol|Where/hoe toegewezen|
|---|---|
|globale beheerder|De persoon die zich registreert voor het kopen van Microsoft 365 is standaard een globale beheerder. (Zie [informatie over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)|
|Beveiligingsbeheerder|Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Beheer van organisatie van Exchange Online|Exchange-Beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

> [!TIP]
> Als u meer wilt weten over rollen en machtigingen, raadpleegt u [machtigingen in de sectie beveiliging & nalevings centrum](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>Een aangepaste lijst met geblokkeerde Url's weergeven of bewerken

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw werk-of schoolaccount.

2. Kies in het linker navigatiegedeelte onder **Threat Management**de optie **beleids** \> **veilige koppelingen**.

3. Selecteer in de sectie **beleidsregels die van toepassing zijn op het hele organigram** de optie **standaard**en kies vervolgens **bewerken** (de knop bewerken lijkt op een potlood).<br/>![Klik op bewerken om uw standaardbeleid te bewerken voor beveiliging van beveiligde koppelingen](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>Hiermee kunt u de lijst met geblokkeerde Url's weergeven. Aanvankelijk zijn er mogelijk geen Url's weergegeven.<br/>![Lijst met geblokkeerde Url's in het standaardbeleid voor veilige koppelingen](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)

4. Selecteer het vak **een geldige URL opgeven** , typ een URL en kies het plusteken ( **+** ).

5. Wanneer u klaar bent met het toevoegen van Url's, kiest u in de rechterbenedenhoek van het scherm de optie **Opslaan**.

## <a name="a-few-things-to-keep-in-mind"></a>Enkele dingen om rekening mee te houden

Let op de volgende punten wanneer u Url's toevoegt aan de lijst:

- Neem geen schuine streep naar **/** het einde van de URL. U kunt bijvoorbeeld niet typen `https://www.contoso.com/` `https://www.contoso.com` .

- U kunt alleen een domein-URL (zoals `contoso.com` of `tailspintoys.com` ) opgeven. Dit blokkeert de klikken op een URL die het domein bevat.

- U kunt een subdomein opgeven (like `toys.contoso.com*` ) zonder dat u een volledig domein (zoals `contoso.com` ) blokkeert. Dit blokkeert de klikken op een URL die het subdomein bevat, maar blokkeert geen klikken op een URL die het volledige domein bevat.

- U kunt maximaal drie jokertekens ( \* ) per URL opnemen. In de volgende tabel ziet u enkele voorbeelden van wat u kunt invoeren en wat van invloed is op de invoer.

****

|Voorbeeld van invoer|Actie|
|---|---|
|`contoso.com` wel `*contoso.com*`|Blokkeert het domein, subdomeinen en paden, zoals `https://www.contoso.com` , `https://sub.contoso.com` en `https://contoso.com/abc`|
|`https://contoso.com/a`|Blokkeert een site `https://contoso.com/a` maar geen extra subpadnamen zoals `https://contoso.com/a/b`|
|`https://contoso.com/a*`|Blokkeert een site `https://contoso.com/a` en extra subpadnamen, zoals `https://contoso.com/a/b`|
|`https://toys.contoso.com*`|Blokkeert een subdomein (' Toys ' in dit geval), maar sta klikken op andere Url's voor het domein (zoals `https://contoso.com` of `https://home.contoso.com` ) toe.|
|

> [!NOTE]
> Standaard kunt u alleen 500-Url's toevoegen aan de lijst met geblokkeerde URL'S in het standaardbeleid van Office 365 voor standaardverbindingen. Een individuele URL mag niet langer zijn dan 128 tekens. De lijst alle geblokkeerde URL'S mag niet langer zijn dan 10.000 tekens.

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>Uitzonderingen definiëren voor bepaalde gebruikers in een organisatie

Als u wilt dat bepaalde groepen Url's kunnen weergeven die mogelijk zijn geblokkeerd voor anderen, kunt u een beleid instellen voor veilige verbindingen voor specifieke geadresseerden. Zie [een aangepaste lijst met behulp van openbare koppelingen voor het maken van Url's instellen](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
