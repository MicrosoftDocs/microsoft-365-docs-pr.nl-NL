---
title: Een aangepaste lijst met niet-herschrijfbare Url's instellen met behulp van behulp van behulp van vrije verbindingen
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
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het instellen van aangepaste geblokkeerde Url's voor gebruikers en het niet-opnieuw schrijven van Url's voor een groep gebruikers in Office 365 ATP-beleid voor veilige koppelingen.
ms.openlocfilehash: 9ec9c92e038aee33c716405916df009e3f4c60c5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825231"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-atp-safe-links"></a>Een aangepaste lijst met niet-herschrijfbare Url's instellen met behulp van behulp van behulp van vrije verbindingen

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Als u een thuisgebruiker bent die op zoek bent naar informatie over veilige koppelingen in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie een aangepaste, [geblokkeerde url's](set-up-a-custom-blocked-urls-list-atp.md)hebben, bijvoorbeeld wanneer mensen klikken op webadressen (url's) in e-mailberichten of bepaalde Office-documenten, kunnen ze niet naar deze url's gaan. Uw organisatie kan ook aangepaste lijsten met niet herschrijven maken voor specifieke groepen in uw organisatie. Met een ' niet herschrijven-lijst kunnen sommige personen Url's bezoeken die [in Office 365](atp-safe-links.md)anders worden geblokkeerd met veilige koppelingen voor ATP.

In dit artikel wordt uitgelegd hoe u een lijst met Url's opgeeft die zijn uitgesloten van een veilige scan van een vrije site en enkele belangrijke punten waarmee u rekening moet houden.

> [!NOTE]
> Als uw organisatie beleidsregels voor veilige koppelingen gebruikt, is de lijst niet herschrijven de enige ondersteunde methode voor phishing van derden.

## <a name="set-up-a-do-not-rewrite-list"></a>Een lijst ' niet herschrijven ' instellen

De bescherming van de standaardbeveiliging van ATP maakt gebruik van diverse lijsten, waaronder de lijst met geblokkeerde Url's van uw organisatie en de lijsten niet herschrijven voor uitzonderingen. Als u over de juiste machtigingen beschikt, kunt u uw aangepaste lijsten ' niet herschrijven ' instellen. U doet dit als u beleidsregels voor veilige koppelingen toevoegt of bewerkt die van toepassing zijn op bepaalde geadresseerden in uw organisatie.

U moet de juiste rol krijgen als u het ATP-beleid wilt bewerken (of definiëren). De volgende tabel bevat enkele voorbeelden. Zie voor meer informatie [machtigingen in de beveiligings & nalevings centrum](permissions-in-the-security-and-compliance-center.md).

|Rol|Where/hoe toegewezen|
|---|---|
|globale beheerder|De persoon die zich registreert voor het kopen van Microsoft 365 is standaard een globale beheerder. (Zie [informatie over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)|
|Beveiligingsbeheerder|Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Beheer van organisatie van Exchange Online|Exchange-Beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

> [!TIP]
> Als u meer wilt weten over rollen en machtigingen, raadpleegt u [machtigingen in de sectie beveiliging & nalevings centrum](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>Een aangepaste lijst met Url's weergeven of bewerken

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan met uw werk-of schoolaccount.

2. Klik in het linker navigatiegedeelte **Threat management** op \> **Policy** \> **veilige koppelingen**onder beleid voor risicobeheer.

3. Kies in de sectie **beleidsregels die gelden voor specifieke geadresseerden** de optie **Nieuw** (de knop Nieuw lijkt op een plusteken ( **+** )) om een nieuw beleid te maken. (U kunt een bestaand beleid ook bewerken.)<br/>![Kies Nieuw om een beleid voor veilige koppelingen toe te voegen voor specifieke e-mail geadresseerden](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

4. Geef een naam en beschrijving voor het beleid op.

5. Url's **inschakelen** worden herschreven en gecontroleerd tegen een lijst met bekende kwaadaardige koppelingen wanneer de gebruiker klikt op de koppeling.

6. Selecteer in de sectie **niet herschrijven de volgende url's** het vak **Voer een geldige URL** in, voer een URL in en kies vervolgens het plusteken (+).

7. Kies in de sectie **toegepast op** **de geadresseerde lid van**en kies vervolgens de groep (en) die u wilt opnemen in uw beleid. Kies **toevoegen**en kies vervolgens **OK**.

8. Wanneer u klaar bent met het toevoegen van Url's, kiest u in de rechterbenedenhoek van het scherm de optie **Opslaan**.

> [!NOTE]
> Zorg ervoor dat u de aangepaste lijst met geblokkeerde Url's van uw organisatie bekijkt. Zie [een aangepaste lijst met geblokkeerde Url's instellen met behulp van veilige koppelingen](set-up-a-custom-blocked-urls-list-atp.md)

## <a name="important-points-to-keep-in-mind"></a>Belangrijke punten waarmee u rekening moet houden

- Url's die u in de lijst ' niet herschrijven ' opgeeft, worden niet opgenomen in de lijst met veilige koppelingen voor de geadresseerden die u opgeeft.

- Overweeg veelgebruikte interne Url's toe te voegen aan de lijst niet herschrijven om de gebruikerservaring te verbeteren. Als u bijvoorbeeld on-premises Services hebt, zoals Skype voor bedrijven of SharePoint, kunt u hun Url's toevoegen aan de lijst, zodat u ze niet kunt scannen.

- Als u al een lijst met Url's hebt in de lijst niet opnieuw schrijven, controleert u de lijst en voegt u de gewenste jokertekens toe. Als uw bestaande lijst bijvoorbeeld een item bevat `https://contoso.com/a` en u wilt ook subpaden opnemen `https://contoso.com/a/b` in uw beleid, voegt u een jokerteken toe aan uw bericht, zodat het er zo uitziet `https://contoso.com/a/*` .

- Wanneer u een lijst ' niet herschrijven ' opgeeft voor een beleid voor veilige verbindingen voor vrije verbindingen, kunt u maximaal drie jokertekens ( \* ) opnemen. Jokertekens zijn expliciet voorvoegsels of subdomeinen. U kunt bijvoorbeeld niet gelijk zijn aan de invoer `contoso.com` `*.contoso.com/*` omdat `*.contoso.com/*` gebruikers subdomeinen en paden kunnen vinden in het opgegeven domein.

De volgende tabel bevat voorbeelden van wat u kunt invoeren en welke gevolgen deze vermeldingen hebben.

****

|Voorbeeld van invoer|Actie|
|---|---|
|`contoso.com`|Hiermee kunnen geadresseerden een site bezoeken, zoals `https://contoso.com` subdomeinen of paden.|
|`*.contoso.com/*`|Hiermee kunnen geadresseerden een domein, subdomeinen en paden bezoeken, bijvoorbeeld,, `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` of `https://www.contoso.com/a` . <br/><br/> Deze vermelding is inherent `*contoso.com*` aan het gebruik, omdat dit geen potentiële frauduleuze sites bevat, zoals `https://www.falsecontoso.com` of `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Hiermee kunnen bepaalde geadresseerden een site niet vinden `https://contoso.com/a` , zoals `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Hiermee kunnen bepaalde geadresseerden een site zoals `https://contoso.com/a` en subpad bezoeken als `https://contoso.com/a/b`|
|
