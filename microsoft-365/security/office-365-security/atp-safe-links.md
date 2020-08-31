---
title: Veilige ATP-koppelingen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: In dit artikel vindt u informatie over het gebruik van veilige koppelingen om uw organisatie tegen phishing en andere aanvallen te beschermen.
ms.openlocfilehash: d9b3c981cb282c286a5b6edcea367c8c57ffd4d3
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307635"
---
# <a name="atp-safe-links"></a>Veilige ATP-koppelingen

## <a name="overview-of-office-365-atp-safe-links"></a>Overzicht van veilige koppelingen in Office 365 ATP

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Als u gebruikmaakt van Outlook.com, Microsoft 365 Family of Microsoft 365 Personal en u op zoek bent naar informatie over veilige koppelingen in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Met behulp van Office 365 ATP voor veilige koppelingen (onderdeel van [Office 365 Advanced Threat Protection](office-365-atp.md)) kunt u uw organisatie beschermen door time-to-click-verificatie van webadressen (url's) te verstrekken in [e-mailberichten](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email) en [Office-documenten](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents). Beveiliging wordt gedefinieerd via profielen voor [veilige koppelingen](set-up-atp-safe-links-policies.md) die zijn ingesteld door uw microsoft 365-beveiligingsteam.

Wanneer uw beleid voor veilige koppelingen voor vrije gebruikers is ingesteld, kunnen globale beheerders, beveiligingsbeheerders en beveiligings lezers [rapporten weergeven voor een geavanceerde bedreigingsbeveiliging](view-reports-for-atp.md). Met de informatie in deze rapporten kunnen uw beveiligingsteam extra stappen ondernemen om uw organisatie te beschermen of beveiligingsincidenten te onderzoeken.

Aangezien [nieuwe functies worden toegevoegd aan ATP](office-365-atp.md#new-features-in-office-365-atp), kunnen uw beveiligingsteam van microsoft 365 het [beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md)van uw organisatie toevoegen of bewerken. Daarnaast zijn er mogelijk wijzigingen en verbeteringen, zoals de nieuwe gereviseerde [waarschuwings pagina's](atp-safe-links-warning-pages.md) en de rendering van native link in Outlook (geïntroduceerd in microsoft 365-apps voor Enterprise versie 1809).

## <a name="how-to-get-atp-safe-links-protection"></a>Hoe u beveiliging van ATP voor veilige koppelingen ontvangt

**Zorg er eerst voor dat uw abonnement [Office 365 Advanced Threat Protection](office-365-atp.md) bevat** Abonnement 1 of abonnement 2. Office 365 ATP is inbegrepen in abonnementen, zoals [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business Premium](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 education A5, enzovoort. Als uw organisatie een Microsoft 365-abonnement heeft dat geen Office 365-ATP bevat, kunt u ATP kopen als een invoegtoepassing. Voor meer informatie raadpleegt u de volgende bronnen: 

- [Office 365 Advanced Threat Protection-abonnementen en-prijzen](https://products.office.com/exchange/advance-threat-protection)

- [Beschrijving van de service Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

**Zorg er vervolgens voor dat u beleidsregels voor veilige koppelingen voor de ATP definieert**. (Zie [beleidsregels voor veilige koppelingen in Office 365 instellen](set-up-atp-safe-links-policies.md).) Functies voor veilige verbindingen voor ATP zijn actief in de volgende situaties:

- Beleidsregels voor veilige koppelingen voor e-mail worden ingesteld voor e-mail-en voor Office-documenten. (Zie [beleid voor veilige koppelingen van ATP instellen](set-up-atp-safe-links-policies.md).)

- Microsoft 365-client-apps zijn geconfigureerd voor het gebruik van moderne verificatie (dit is voor veilige koppelingen in Office-documenten). (Zie [moderne verificatie voor Office 2016](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).)

- Gebruikers hebben zich aangemeld met hun werk-of schoolaccount. (Zie [Aanmelden bij Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).)

- De e-mail van uw organisatie wordt doorgestuurd via Exchange Online Protection.

**Zorg er ook voor dat u over de benodigde machtigingen beschikt**. Als u ATP-beleidsregels wilt definiëren (of bewerken), moet aan u de juiste rol zijn toegewezen. In de volgende tabel worden enkele voorbeelden beschreven:

****

|Rol|Where/hoe toegewezen|
|---|---|
|globale beheerder|De persoon die zich registreert voor het kopen van Microsoft 365 is standaard een globale beheerder. (Zie [informatie over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)|
|Beveiligingsbeheerder|Azure Active Directory-beheercentrum ( <https://aad.portal.azure.com> )|
|Beheer van organisatie van Exchange Online|Exchange-Beheercentrum ( <https://outlook.office365.com/ecp> ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Garanderen dat de bescherming van de veilige beveiliging van ATP wordt uitgevoerd

Als globale beheerder of beveiligingsbeheerder controleert u de [beleidsregels voor veilige koppelingen](set-up-atp-safe-links-policies.md) regelmatig op. Met beleidsregels voor veilige koppelingen wordt bepaald of beveiliging alleen geldt voor hyperlinks in e-mailberichten, of naar Url's in Office-documenten.

Wanneer beleidsregels voor veilige koppelingen voor ATP zijn ingesteld, kan het beveiligingsteam van uw organisatie zien hoe de bescherming van een veilige beveiliging voor uw organisatie werkt, door [rapporten te bekijken voor Advanced Threat Protection](view-reports-for-atp.md)

## <a name="example-scenarios"></a>Voorbeelden van scenario's

In de volgende tabel worden enkele voorbeeldscenario's beschreven waarbij beveiligingskoppelingen met ATP mogelijk niet aanwezig zijn. (In al deze gevallen wordt ervan uitgegaan dat de organisatie Office 365 Enterprise E5 heeft.)

****

|Voorbeeld van scenario|Is er sprake van de bescherming van ATP voor veilige koppelingen van toepassing?|
|---|---|
|Jean is een lid van een groep met beleidsregels voor veilige koppelingen met ATP en Url's in e-mail-en Office-documenten. Met Jean opent u een PowerPoint-presentatie die door iemand is verzonden en klik vervolgens op een URL in de presentatie.|Ja. Het beleid voor veilige koppelingen voor apps die zijn gedefinieerd voor de groep, de e-mail van de groepen Jean, e-mailberichten en Word-, Excel-, PowerPoint-of Visio-documenten die met Jean worden geopend, zo lang Jean is aangemeld en Microsoft 365-apps gebruiken voor Enterprise op Windows-, iOS-of Android-apparaten.|
|In de organisatie van Chris zijn er nog geen globale beheerders en beveiligingsbeheerders ingesteld op de beleidsregels voor veilige koppelingen. Chris ontvangt een e-mailbericht dat een URL naar een schadelijke website bevat. Chris is niet bekend dat de URL schadelijk is en op de koppeling klikt.|Nee. Het standaardbeleid voor het opslaan van Url's voor iedereen in de organisatie moet worden gedefinieerd om de beveiliging te kunnen hebben.|
|In de organisatie van de Pat zijn er nog geen globale beheerders en beveiligingsbeheerders ingesteld of bewerkt u beleidsregels voor veilige koppelingen. Pat opent een Word-document en klikt op een URL in het bestand.|Nee. Een beleid dat Office-documenten bevat, moet worden gedefinieerd om de beveiliging binnen te laten. Zie [beleidsregels voor veilige koppelingen instellen in Office 365](set-up-atp-safe-links-policies.md).|
|De organisatie van Lee heeft een beleid voor veilige verbindingen voor de vrije organisatie dat is `https://tailspintoys.com` vermeld als een geblokkeerde website. Lee ontvangt een e-mailbericht dat een URL bevat `https://tailspintoys.com/aboutus/trythispage` . Lee: klikken op de URL.|Het hangt af van het feit of de volledige site en alle bijbehorende subpagina's in de lijst met geblokkeerde Url's zijn opgenomen. Zie [een aangepaste lijst met geblokkeerde Url's instellen met behulp van veilige koppelingen](set-up-a-custom-blocked-urls-list-atp.md)|
|Janny, Jean, verzendt een e-mailbericht naar Jean, en weet niet dat het e-mailbericht een schadelijke URL bevat.|Het is afhankelijk van het feit of beleidsregels voor veilige verbindingen worden gedefinieerd voor e-mail die binnen de organisatie wordt verzonden. Zie [beleidsregels voor veilige koppelingen instellen in Office 365](set-up-atp-safe-links-policies.md).|
|
