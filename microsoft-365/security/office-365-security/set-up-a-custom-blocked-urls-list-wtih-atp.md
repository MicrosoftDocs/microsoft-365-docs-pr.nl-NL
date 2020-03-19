---
title: Een aangepaste geblokkeerde URL'slijst instellen met Office 365 ATP Safe Links
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
description: Meer informatie over het instellen van een lijst met geblokkeerde URL's voor uw organisatie met behulp van Office 365 Advanced Threat Protection. De geblokkeerde URL's zijn van toepassing op e-mailberichten en Office-documenten volgens uw ATP-beleid voor veilige koppelingen.
ms.openlocfilehash: 5205fbd5ccc873513eed4e367119084516e92bf2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809857"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>Een aangepaste geblokkeerde URL'slijst instellen met Office 365 ATP Safe Links

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md)hebben. Zie [Geavanceerde Outlook.com beveiliging](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)als u een thuisgebruiker bent die op zoek is naar informatie over veilige koppelingen in Outlook.

Met [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kan uw organisatie een aangepaste lijst met websiteadressen (URL's) hebben die zijn geblokkeerd. Wanneer een URL wordt geblokkeerd, worden mensen die op koppelingen naar de geblokkeerde URL klikken naar een [waarschuwingspagina](atp-safe-links-warning-pages.md) geleid die lijkt op de volgende afbeelding: 
  
![Deze site is geblokkeerd](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
De geblokkeerde URL'slijst wordt gedefinieerd door het Office 365-beveiligingsteam van uw organisatie en die lijst is van toepassing op iedereen in de organisatie die onder het beleid voor veilig beveiligde koppelingen van Office 365 valt. 
  
Lees dit artikel voor meer informatie over het instellen van de aangepaste geblokkeerde URL'slijst van uw organisatie voor [ATP Safe Links in Office 365.](atp-safe-links.md)
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>Een aangepaste lijst met geblokkeerde URL's weergeven of bewerken

[ATP Safe Links in Office 365](atp-safe-links.md) gebruikt verschillende lijsten, waaronder de aangepaste geblokkeerde URL's lijst van uw organisatie. Als u over de benodigde machtigingen beschikt, u de aangepaste lijst van uw organisatie instellen. U doet dit door het standaard beleid voor veilige koppelingen van uw organisatie te bewerken.

Als u het ATP-beleid wilt bewerken (of definiëren), moet u een van de rollen toegewezen krijgen die in de volgende tabel worden beschreven: 

|Rol  |Waar/hoe toegewezen  |
|---------|---------|
|Globale beheerder van Office 365 |De persoon die zich aanmeldt om Office 365 te kopen, is standaard een globale beheerder. (Zie [Informatie over office 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)         |
|Beveiligingsbeheerder |Azure Active Directory-beheercentrum ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online Organisatiebeheer |Exchange-beheercentrum[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)( ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |

> [!TIP]
> Zie Machtigingen in het Office [365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>Een aangepaste geblokkeerde URL'slijst weergeven of bewerken
  
1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan met je werk- of schoolaccount. 
    
2. Kies in de linkernavigatie onder **Bedreigingsbeheer**de optie **Veilig beleid** \> **links**.
    
3. Selecteer **standaard**in de sectie **Beleid dat van toepassing is op de hele organisatiesectie** en kies **Bewerken** (de knop Bewerken lijkt op een potlood).<br/>![Klik op Bewerken om uw standaardbeleid voor beveiliging van veilige koppelingen te bewerken](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>Hiermee u uw lijst met geblokkeerde URL's bekijken. In eerste instantie u hier geen URL's laten vermelden.<br/>![Geblokkeerde URL's lijst in het standaardbeleid voor veilige koppelingen](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. Selecteer het vak **Een geldige URL invoeren,** typ een**+** URL en kies het plusteken ( ). 

5. Wanneer u klaar bent met het toevoegen van URL's, kiest u in de rechterbenedenhoek van het scherm **Opslaan**.
    
## <a name="a-few-things-to-keep-in-mind"></a>Een paar dingen om in gedachten te houden

Houd rekening met de volgende punten terwijl u URL's aan uw lijst toevoegt: 

- Voeg geen voorwaartse **/** slash () toe aan het einde van de URL. In plaats van `https://www.contoso.com/`bijvoorbeeld `https://www.contoso.com`in te voeren , voer .
    
- U een URL die `contoso.com` alleen `tailspintoys.com`voor domeinen wordt opgegeven (zoals of ). Hiermee worden klikken op een URL die het domein bevat, geblokkeerd.

- U een subdomein `toys.contoso.com*`opgeven (zoals) zonder `contoso.com`een volledig domein te blokkeren (zoals ). Hiermee wordt op een URL die het subdomein bevat, geblokkeerd, maar wordt er geen klikken geblokkeerd naar een URL die het volledige domein bevat.  
    
- U maximaal drie wildcard sterretjes opnemen (\*) per URL. In de volgende tabel worden enkele voorbeelden weergegeven van wat u invoeren en welk effect deze vermeldingen hebben.
    
|**Voorbeelditem**|**Wat het doet**|
|:-----|:-----|
|`contoso.com`Of`*contoso.com*`  <br/> |Blokkeert het domein, subdomeinen en `https://www.contoso.com`paden, zoals , `https://sub.contoso.com`en`https://contoso.com/abc`  <br/> |
|`https://contoso.com/a`  <br/> |Blokkeert een `https://contoso.com/a` site, maar geen extra subpaden zoals`https://contoso.com/a/b`  <br/> |
|`https://contoso.com/a*`  <br/> |Blokkeert een `https://contoso.com/a` site en extra subpaden zoals`https://contoso.com/a/b`  <br/> |
|`https://toys.contoso.com*`  <br/> |Blokkeert een subdomein ("speelgoed" in dit geval), maar staat `https://contoso.com` `https://home.contoso.com`klikken toe naar andere domein-URL's (zoals of ).  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>Uitzonderingen definiëren voor bepaalde gebruikers in een organisatie

Als u wilt dat bepaalde groepen URL's kunnen weergeven die mogelijk voor anderen worden geblokkeerd, u een ATP-beleid voor veilige koppelingen opgeven dat van toepassing is op specifieke ontvangers. Zie [Een aangepaste URL's-lijst 'Niet herschrijven' instellen met behulp van ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
  

