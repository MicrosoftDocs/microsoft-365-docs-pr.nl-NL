---
title: Office 365 ATP Veilige koppelingen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: De functie Veilige koppelingen biedt tijd-van-klikverificatie van hyperlinks in Office-documenten en in e-mailberichten. Gebruik Veilige koppelingen om uw organisatie te beschermen tegen phishing en andere aanvallen.
ms.openlocfilehash: 5834c3c49529f983d426084a50712c55de92fc63
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810428"
---
# <a name="office-365-atp-safe-links"></a>Office 365 ATP Veilige koppelingen

## <a name="overview-of-office-365-atp-safe-links"></a>Overzicht van veilige koppelingen naar Office 365 ATP

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md)hebben. Zie [Geavanceerde Outlook.com beveiliging](https://support.office.com/article/882d2243-eab9-4545-a58a-b36fee4a46e2)als u Outlook.com, Office 365 Home of Office 365 Personal gebruikt en op zoek bent naar informatie over veilige koppelingen in Outlook.

Office 365 ATP Safe Links (onderdeel van [Advanced Threat Protection)](office-365-atp.md)kan uw organisatie helpen beschermen door tijd-van-klikverificatie van webadressen (URL's) in [e-mailberichten](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email) en [Office-documenten](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents)te bieden. Beveiliging wordt gedefinieerd door [het ATP-beleid](set-up-atp-safe-links-policies.md) voor veilige koppelingen dat is ingesteld door uw Office 365-beveiligingsteam.
  
Zodra uw ATP-beleid voor veilige koppelingen is ingevoerd, kunnen wereldwijde beheerders, beveiligingsbeheerders en beveiligingslezers [rapporten voor geavanceerde bedreigingsbeveiliging bekijken.](view-reports-for-atp.md) De informatie in die rapporten kan uw beveiligingsteam helpen verdere stappen te ondernemen om uw organisatie- of onderzoeksbeveiligingsincidenten te beschermen.

Als [nieuwe functies aan ATP worden toegevoegd,](office-365-atp.md#new-features-in-office-365-atp)kan uw Office 365-beveiligingsteam het [ATP-beleid](set-up-atp-safe-links-policies.md)voor veilige links van uw organisatie toevoegen of bewerken. Daarnaast ziet u mogelijk wijzigingen en verbeteringen, zoals onze nieuw herziene [waarschuwingspagina's](atp-safe-links-warning-pages.md) en native linkrendering in Outlook (geïntroduceerd in Office 365 ProPlus-versie 1809).
         
## <a name="how-to-get-atp-safe-links-protection"></a>Bescherming tegen ATP Safe Links

**Zorg er eerst voor dat uw abonnement [geavanceerde bedreigingsbescherming](office-365-atp.md)bevat.** ATP is opgenomen in abonnementen, zoals [Microsoft 365 Enterprise,](https://www.microsoft.com/microsoft-365/enterprise/home) [Microsoft 365 Business,](https://www.microsoft.com/microsoft-365/business)Office 365 Enterprise E5, Office 365 Education A5, enz. Als uw organisatie een Office 365-abonnement heeft dat office 365 ATP niet bevat, u ATP mogelijk als bijtelling aanschaffen. Zie de volgende bronnen voor meer informatie: 

- [Office 365 Advanced Threat Protection-abonnementen en -prijzen](https://products.office.com/exchange/advance-threat-protection)

- [Beschrijving van office 365-geavanceerde service voor bedreigingsbeveiliging](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 
  
**Controleer vervolgens of uw ATP-beleid voor veilige koppelingen is gedefinieerd.** (Zie [Beleid voor veilig links van Office 365 instellen](set-up-atp-safe-links-policies.md).) ATP Safe Links-functies zijn actief wanneer:
  
- Atp-beleid voor veilige koppelingen is ingesteld voor e-mail en office-documenten. (Zie [BELEID VOOR veilig verbanden met ATP instellen in Office 365](set-up-atp-safe-links-policies.md).)

- Office 365-client-apps zijn geconfigureerd om moderne verificatie te gebruiken (dit is voor ATP Safe Links-beveiliging in Office-documenten). (Zie [Moderne verificatie voor Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).) 
    
- Gebruikers hebben zich aangemeld bij Office 365 met hun werk- of schoolaccount. (Zie [Aanmelden bij Office of Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)
    
- De e-mail van uw organisatie gaat door Exchange Online Protection.  

**Zorg er ook voor dat u over de nodige machtigingen**beschikt. Als u het ATP-beleid wilt definiëren (of bewerken), moet u een geschikte rol toegewezen krijgen. Enkele voorbeelden worden beschreven in de volgende tabel:

|Rol  |Waar/hoe toegewezen  |
|---------|---------|
|Globale beheerder van Office 365 |De persoon die zich aanmeldt om Office 365 te kopen, is standaard een globale beheerder. (Zie [Informatie over office 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)         |
|Beveiligingsbeheerder |Azure Active Directory-beheercentrum ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online Organisatiebeheer |Exchange-beheercentrum[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)( ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Hoe zorg je ervoor dat ATP Safe Links bescherming is op zijn plaats

Als globale beheerder of beveiligingsbeheerder moet u regelmatig uw [ATP Safe Links-beleid](set-up-atp-safe-links-policies.md) controleren. Atp-beleid voor veilige koppelingen bepaalt of de beveiliging alleen van toepassing is op hyperlinks in e-mailberichten of op URL's in Office-documenten.

Nadat het ATP Safe Links-beleid is ingevoerd, kan het beveiligingsteam van uw organisatie zien hoe ATP Safe Links-beveiliging werkt voor uw organisatie door [rapporten voor geavanceerde bedreigingsbescherming](view-reports-for-atp.md)te bekijken. 

## <a name="example-scenarios"></a>Voorbeelden van scenario's
  
In de volgende tabel worden enkele voorbeeldscenario's beschreven waarin de atp-beveiliging voor veilige koppelingen al dan niet aanwezig is. (In al deze gevallen gaan we ervan uit dat de organisatie Office 365 Enterprise E5 heeft.)
  
|**Voorbeeldscenario**|**Is atp safe links bescherming van toepassing in dit geval?**|
|:-----|:-----|
|Jean is lid van een groep met een ATP Safe Links-beleid voor URL's in e-mail- en Office-documenten. Jean opent een PowerPoint-presentatie die iemand heeft verzonden en klikt vervolgens op een URL in de presentatie.  <br/> |Ja. Het ATP-beleid voor veilige koppelingen dat is gedefinieerd, is van toepassing op de groep van Jean, de e-mail van Jean en de Word-, Excel-, PowerPoint- of Visio-documenten die Jean opent, zolang Jean is aangemeld en Office 365 ProPlus gebruikt op Windows-, iOS- of Android-apparaten.  <br/> |
|In de organisatie van Chris hebben nog geen globale of beveiligingsbeheerders een ATP-beleid voor veilige koppelingen gedefinieerd. Chris ontvangt een e-mail met een URL naar een kwaadaardige website. Chris is zich niet bewust van de URL is kwaadaardig en klikt op de link.  <br/> |Nee. Het standaardbeleid dat URL's dekt voor iedereen in de organisatie moet worden gedefinieerd om de beveiliging te kunnen bieden.  <br/> |
|In de organisatie van Pat hebben nog geen globale of beveiligingsbeheerders een ATP Safe Links-beleid gedefinieerd of bewerkt. Pat opent een Word-document en klikt op een URL in het bestand.  <br/> |Nee. Er moet een beleid worden gedefinieerd dat Office-documenten bevat om de bescherming te kunnen bieden. Zie BELEID VOOR VEILIG AFsteken VAN [ATP instellen in Office 365](set-up-atp-safe-links-policies.md).  <br/> |
|Lee's organisatie heeft een ATP `https://tailspintoys.com` Safe Links beleid dat is vermeld als een geblokkeerde website. Lee ontvangt een e-mailbericht `https://tailspintoys.com/aboutus/trythispage`met een URL naar . Lee klikt op de URL.  <br/> |Het hangt af van de vraag of de hele site en alle subpagina's zijn opgenomen in de lijst met geblokkeerde URL's. Zie [Een aangepaste geblokkeerde URL'slijst instellen met BEHULP VAN ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).  <br/> |
|Jamie, Jean's collega, stuurt een e-mail naar Jean, niet wetende dat de e-mail bevat een kwaadaardige URL.  <br/> |Het hangt ervan af of het ATP-beleid voor veilige koppelingen is gedefinieerd voor e-mail die binnen de organisatie wordt verzonden. Zie BELEID VOOR VEILIG AFsteken VAN [ATP instellen in Office 365](set-up-atp-safe-links-policies.md).  <br/> |


  

