---
title: Een aangepaste lijst met URL's die niet opnieuw worden herschreven instellen met atp-veilige koppelingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het instellen van aangepaste geblokkeerde URL's voor gebruikers en het niet herschrijven van de lijst met URL's voor een groep gebruikers in het beleid voor veilige koppelingen met Office 365 ATP.
ms.openlocfilehash: c75f468aa98c8fa9e45cd596c62a7509310fdca5
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588130"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a>Een aangepaste lijst met URL's die niet opnieuw worden herschreven instellen met atp-veilige koppelingen

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Zie [Geavanceerde Outlook.com beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige koppelingen.

Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie een aangepaste [geblokkeerde URL's](set-up-a-custom-blocked-urls-list-atp.md)hebben, zodat wanneer mensen op webadressen (URL's) in e-mailberichten of bepaalde Office-documenten klikken, ze niet naar die URL's kunnen gaan. Uw organisatie kan ook aangepaste 'niet herschrijven' lijsten voor specifieke groepen in uw organisatie hebben. Met een lijst 'niet herschrijven' kunnen sommige mensen URL's bezoeken die anders worden geblokkeerd door [ATP Safe Links in Office 365.](atp-safe-links.md)

In dit artikel wordt beschreven hoe u een lijst met URL's opgeeft die zijn uitgesloten van het scannen van ATP Safe Links en een paar belangrijke punten om in gedachten te houden.

## <a name="set-up-a-do-not-rewrite-list"></a>Een lijst 'niet herschrijven' instellen

Atp Safe Links-beveiliging maakt gebruik van verschillende lijsten, waaronder de lijst met geblokkeerde URL's van uw organisatie en de lijsten 'niet herschrijven' voor uitzonderingen. Als u over de benodigde machtigingen beschikt, u uw aangepaste lijsten 'niet herschrijven' instellen. Dit doe je wanneer u het beleid voor veilige koppelingen toevoegt of bewerkt dat van toepassing is op specifieke ontvangers in uw organisatie.

Als u ATP-beleid wilt bewerken (of definiëren), moet u een geschikte rol toegewezen krijgen. De volgende tabel bevat enkele voorbeelden. Zie [Machtigingen in het Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie.

|Rol  |Waar/hoe toegewezen  |
|---------|---------|
|globale beheerder |De persoon die zich aanmeldt om Microsoft 365 te kopen, is standaard een globale beheerder. (Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)         |
|Beveiligingsbeheerder |Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Exchange Online Organisatiebeheer |Exchange-beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

> [!TIP]
> Zie [Machtigingen in het Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>Een aangepaste URL'slijst 'niet herschrijven' weergeven of bewerken

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan met je werk- of schoolaccount.

2. In de linker navigatie, onder **Threat management** \> **Policy** \> **Safe Links**.

3. Kies Nieuw (de knop **Nieuw** lijkt op een plusteken ( )) in de sectie **Beleid dat van toepassing is op specifieke geadresseerden** **+** om een nieuw beleid te maken. (U ook een bestaand beleid bewerken.)<br/>![Kies Nieuw om een beleid voor veilige koppelingen toe te voegen voor specifieke e-mailontvangers](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. Geef een naam en beschrijving op voor uw polis.

5. Selecteer in de sectie **De volgende URL's niet herschrijven** het vak **Een geldige URL invoeren** en typ vervolgens een URL en kies het plusteken (+).

6. Kies in de sectie **Toegepast op** de ontvanger **lid van**de groep(en) die u in uw polis wilt opnemen. Kies **Toevoegen**en kies **vervolgens OK**.

7. Wanneer u klaar bent met het toevoegen van URL's, kiest u in de rechterbenedenhoek van het scherm **Opslaan**.

> [!NOTE]
> Controleer de aangepaste lijst met geblokkeerde URL's van uw organisatie. Zie [Een aangepaste lijst met geblokkeerde URL's instellen met ATP-veilige koppelingen](set-up-a-custom-blocked-urls-list-atp.md).

## <a name="important-points-to-keep-in-mind"></a>Belangrijke punten om in gedachten te houden

- URL's die u opgeeft in de lijst 'niet herschrijven' zijn uitgesloten van het scannen van ATP Safe Links voor de ontvangers die u opgeeft.

- Als u al een lijst met URL's in uw lijst 'niet herschrijven' hebt, moet u die lijst bekijken en wildcards toevoegen. Als uw bestaande lijst bijvoorbeeld een vermelding heeft zoals `https://contoso.com/a` en u subpaden zoals in uw beleid wilt `https://contoso.com/a/b` opnemen, voegt u een wildcard toe aan uw item zodat het eruit ziet `https://contoso.com/a/*` als .

- Wanneer u een lijst 'niet herschrijven' opgeeft voor een ATP-beleid voor veilige koppelingen, u maximaal drie wildcardsterpakken \* (). Jokertekens ( \* ) worden gebruikt om expliciet voorvoegsels of subdomeinen op te nemen. De vermelding `contoso.com` is niet hetzelfde als `*.contoso.com/*` , omdat mensen `*.contoso.com/*` subdomeinen en paden in het opgegeven domein kunnen bezoeken.

In de volgende tabel worden voorbeelden weergegeven van wat u invoeren en welk effect deze vermeldingen hebben.

|**Voorbeeldvermelding**|**Wat het doet**|
|:-----|:-----|
|`contoso.com`|Hiermee kunnen ontvangers een site bezoeken, `https://contoso.com` maar geen subdomeinen of paden.|
|`*.contoso.com/*`|Hiermee kunnen ontvangers een domein, subdomeinen en paden bezoeken, zoals `https://www.contoso.com` , `https://www.contoso.com` , of `https://maps.contoso.com` `https://www.contoso.com/a` . <br/><br/> Dit item is inherent beter `*contoso.com*` dan, omdat het geen potentieel frauduleuze sites bevat, zoals `https://www.falsecontoso.com` of`https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Hiermee kunnen specifieke ontvangers een site bezoeken zoals `https://contoso.com/a` , maar geen subpaden zoals`https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Hiermee kunnen specifieke ontvangers een site zoals `https://contoso.com/a` en subpaden bezoeken, zoals`https://contoso.com/a/b`|
