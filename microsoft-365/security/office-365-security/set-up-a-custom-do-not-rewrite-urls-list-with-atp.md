---
title: Een aangepaste lijst met niet-herschrijven url's instellen met BEHULP van ATP Safe Links
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
description: Meer informatie over het instellen van aangepaste geblokkeerde URL's voor gebruikers en het niet herschrijven van de lijst met URL's voor een groep gebruikers in het beleid voor veilige koppelingen van Office 365 ATP.
ms.openlocfilehash: d7bd6c7d4c3dccfb4a16b2b2f172f8f75123692e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046302"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a>Een aangepaste lijst met niet-herschrijven url's instellen met BEHULP van ATP Safe Links

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Zie [Geavanceerde Outlook.com beveiliging](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige koppelingen in Outlook.

Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie een aangepaste [geblokkeerde URL's](set-up-a-custom-blocked-urls-list-atp.md)hebben, zodat wanneer mensen op webadressen (URL's) klikken in e-mailberichten of bepaalde Office-documenten, ze niet naar die URL's kunnen gaan. Uw organisatie kan ook aangepaste lijsten 'niet herschrijven' voor specifieke groepen in uw organisatie hebben. Met een lijst 'niet herschrijven' kunnen sommige mensen URL's bezoeken die anders worden geblokkeerd door [ATP Safe Links in Office 365.](atp-safe-links.md)

In dit artikel wordt beschreven hoe u een lijst met URL's opgeeft die zijn uitgesloten van het scannen van ATP Safe Links en een paar belangrijke punten om in gedachten te houden.

## <a name="set-up-a-do-not-rewrite-list"></a>Een lijst 'niet herschrijven' instellen

Atp Safe Links protection maakt gebruik van verschillende lijsten, waaronder de geblokkeerde URL's lijst van uw organisatie en de lijsten 'niet herschrijven' voor uitzonderingen. Als u over de benodigde machtigingen beschikt, u uw aangepaste lijsten 'niet herschrijven' instellen. Dit doe je wanneer je beleid voor veilige koppelingen toevoegt of bewerkt dat van toepassing is op specifieke ontvangers in je organisatie.

Als u ATP-beleid wilt bewerken (of definiëren), moet u een geschikte rol toegewezen krijgen. De volgende tabel bevat enkele voorbeelden. Zie [Machtigingen in het Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie.

|Rol  |Waar/hoe toegewezen  |
|---------|---------|
|globale beheerder |De persoon die zich aanmeldt om Microsoft 365 te kopen is standaard een globale beheerder. (Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)         |
|Beveiligingsbeheerder |Azure Active Directory-beheercentrum ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online Organisatiebeheer |Exchange-beheercentrum[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)( ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell)](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell) |

> [!TIP]
> Zie [Machtigingen in het Beveiligings& Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>Een aangepaste URL-lijst 'niet herschrijven' weergeven of bewerken

1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan met je werk- of schoolaccount.

2. In de linkernavigatie, onder **Bedreigingsbeheer** \> **Beleid** \> **Veilige Links**.

3. **Kies** Nieuw (de knop Nieuw lijkt op een plusteken ( **+**)) om een nieuw beleid te maken in de sectie Beleid dat van toepassing is op specifieke **ontvangers.** (U ook een bestaand beleid bewerken.)<br/>![Nieuw kiezen om een beleid voor veilige koppelingen toe te voegen voor specifieke e-mailontvangers](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. Geef een naam en beschrijving op voor uw beleid.

5. Selecteer in de sectie **De volgende URL's niet opnieuw schrijven** het vak Een geldige URL **invoeren** en typ vervolgens een URL en kies het plusteken (+).

6. Kies **in** de sectie Toegepast op **De ontvanger is lid van**, en kies vervolgens de groep(en) die u in uw beleid wilt opnemen. Kies **Toevoegen**en kies **OK**.

7. Wanneer u klaar bent met het toevoegen van URL's, kiest u in de rechterbenedenhoek van het scherm **Opslaan**.

> [!NOTE]
> Controleer de aangepaste lijst met geblokkeerde URL's van uw organisatie. Zie [Een aangepaste geblokkeerde URL-lijst instellen met ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).

## <a name="important-points-to-keep-in-mind"></a>Belangrijke punten om in gedachten te houden

- Alle URL's die u opgeeft in de lijst 'niet herschrijven' zijn uitgesloten van het scannen van ATP Safe Links op de opgegeven ontvangers.

- Als u al een lijst met URL's in uw lijst 'niet herschrijven' hebt staan, moet u die lijst bekijken en wildcards toevoegen. Als uw bestaande lijst bijvoorbeeld een `https://contoso.com/a` vermelding heeft zoals en `https://contoso.com/a/b` u subpaden wilt opnemen zoals in `https://contoso.com/a/*`uw beleid, voegt u een wildcard toe aan uw vermelding, zodat het lijkt op .

- Wanneer u een lijst 'niet herschrijven' opgeeft voor een ATP Safe Links-beleid, u maximaal drie sterretjes (niet\*herschrijven. Wildcards\*( ) worden gebruikt om expliciet voorvoegsels of subdomeinen op te nemen. De `contoso.com` vermelding is niet `*.contoso.com/*`hetzelfde als , omdat `*.contoso.com/*` mensen subdomeinen en paden in het opgegeven domein kunnen bezoeken.

In de volgende tabel worden voorbeelden weergegeven van wat u invoeren en welk effect deze vermeldingen hebben.

|**Voorbeeldvermelding**|**Wat het doet**|
|:-----|:-----|
|`contoso.com`|Hiermee kunnen ontvangers een `https://contoso.com` site bezoeken, zoals, maar niet subdomeinen of paden.|
|`*.contoso.com/*`|Hiermee kunnen ontvangers een domein, subdomeinen en `https://www.contoso.com` `https://www.contoso.com`paden `https://maps.contoso.com`bezoeken, zoals , , of `https://www.contoso.com/a`. <br/><br/> Dit item is inherent `*contoso.com*`beter dan , omdat het niet `https://www.falsecontoso.com` mogelijk frauduleuze sites, zoals of`https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Hiermee kunnen specifieke ontvangers `https://contoso.com/a`een site bezoeken zoals , maar geen subpaden zoals`https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Hiermee kunnen specifieke ontvangers `https://contoso.com/a` een site zoals en subpaden zoals`https://contoso.com/a/b`|
