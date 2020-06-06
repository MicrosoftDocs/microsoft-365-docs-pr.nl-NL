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
description: In dit artikel leert u hoe u veilige koppelingen gebruiken om uw organisatie te beschermen tegen phishing en andere aanvallen.
ms.openlocfilehash: f71ff8d625c6c365f39fd581f3483c8a0384d817
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587542"
---
# <a name="atp-safe-links"></a>Veilige ATP-koppelingen

## <a name="overview-of-office-365-atp-safe-links"></a>Overzicht van veilige office 365-atp-koppelingen

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Als u Outlook.com, Microsoft 365 Family of Microsoft 365 Personal gebruikt en u op zoek bent naar informatie over veilige koppelingen in Outlook, [raadpleegt u Geavanceerde beveiliging Outlook.com](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Office 365 ATP Safe Links (onderdeel van [Office 365 Advanced Threat Protection)](office-365-atp.md)kan uw organisatie helpen beschermen door tijd-van-klik verificatie van webadressen (URL's) in [e-mailberichten](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email) en [Office-documenten](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents)te bieden. Beveiliging wordt gedefinieerd via [atp-beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md) dat is ingesteld door uw Microsoft 365-beveiligingsteam.

Zodra uw ATP-beleid voor veilige koppelingen is ingevoerd, kunnen wereldwijde beheerders, beveiligingsbeheerders en [beveiligingslezers rapporten voor geavanceerde bedreigingsbeveiliging bekijken.](view-reports-for-atp.md) De informatie in deze rapporten kan uw beveiligingsteam helpen verdere stappen te ondernemen om uw organisatie of beveiligingsincidenten te beschermen.

Als [er nieuwe functies worden toegevoegd aan ATP,](office-365-atp.md#new-features-in-office-365-atp)kan uw Microsoft 365-beveiligingsteam het [ATP Safe Links-beleid](set-up-atp-safe-links-policies.md)van uw organisatie toevoegen of bewerken. Daarnaast ziet u mogelijk wijzigingen en verbeteringen, zoals onze onlangs herziene [waarschuwingspagina's](atp-safe-links-warning-pages.md) en native link rendering in Outlook (geïntroduceerd in Microsoft 365 Apps for enterprise versie 1809).

## <a name="how-to-get-atp-safe-links-protection"></a>Hoe atp safe links bescherming te krijgen

**Controleer eerst of uw abonnement [Geavanceerde bedreigingsbeveiliging van Office 365](office-365-atp.md) bevat** Plan 1 of Plan 2. Office 365 ATP is inbegrepen in abonnementen, zoals [Microsoft 365 Enterprise,](https://www.microsoft.com/microsoft-365/enterprise/home) [Microsoft 365 Business Premium,](https://www.microsoft.com/microsoft-365/business)Office 365 Enterprise E5, Office 365 Education A5, enz. Als uw organisatie een Microsoft 365-abonnement heeft dat geen Office 365 ATP bevat, u atp mogelijk als add-on aanschaffen. Zie de volgende bronnen voor meer informatie:

- [Office 365 Advanced Threat Protection-abonnementen en -prijzen](https://products.office.com/exchange/advance-threat-protection)

- [Beschrijving van de Geavanceerde service voor bedreigingsbeveiliging van Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

**Zorg er vervolgens voor dat uw ATP-beleid voor veilige koppelingen is gedefinieerd.** (Zie [Beleid voor OFFICE 365 ATP-veilige koppelingen instellen](set-up-atp-safe-links-policies.md).) ATP Safe Links-functies zijn actief wanneer:

- Atp Safe Links-beleid is ingesteld voor e-mail en office-documenten. (Zie [Beleid voor veilige koppelingen van ATP instellen](set-up-atp-safe-links-policies.md).)

- Microsoft 365-client-apps zijn geconfigureerd voor het gebruik van moderne verificatie (dit is voor de bescherming van ATP Safe Links in Office-documenten). (Zie [Moderne verificatie voor Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)

- Gebruikers hebben zich aangemeld met hun werk- of schoolaccount. (Zie [Aanmelden bij Office of Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)

- De e-mail van uw organisatie gaat via Exchange Online Protection.

**Zorg er ook voor dat je de nodige machtigingen hebt.** Als u ATP-beleid wilt definiëren (of bewerken), moet u een geschikte rol toegewezen krijgen. Enkele voorbeelden worden beschreven in de volgende tabel:

|Rol|Waar/hoe toegewezen|
|---------|---------|
|globale beheerder|De persoon die zich aanmeldt om Microsoft 365 te kopen, is standaard een globale beheerder. (Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)|
|Beveiligingsbeheerder|Azure Active Directory-beheercentrum ( <https://aad.portal.azure.com> )|
|Exchange Online Organisatiebeheer|Exchange-beheercentrum ( <https://outlook.office365.com/ecp> ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>Hoe zorg je ervoor dat atp-beveiliging voor veilige links aanwezig is

Als globale beheerder of beveiligingsbeheerder moet u uw [ATP Safe Links-beleid](set-up-atp-safe-links-policies.md) regelmatig controleren. Atp Safe Links-beleid bepaalt of bescherming alleen van toepassing is op hyperlinks in e-mailberichten of op URL's in Office-documenten.

Nadat het BELEID voor veilige koppelingen van ATP is ingevoerd, kan het beveiligingsteam van uw organisatie zien hoe de bescherming van ATP Safe Links voor uw organisatie werkt door [rapporten voor Geavanceerde bedreigingsbeveiliging te bekijken.](view-reports-for-atp.md)

## <a name="example-scenarios"></a>Voorbeelden van scenario's

In de volgende tabel worden enkele voorbeeldscenario's beschreven waarin de bescherming van ATP-veilige koppelingen al dan niet is ingevoerd. (In al deze gevallen gaan we ervan uit dat de organisatie Office 365 Enterprise E5 heeft.)

|**Voorbeeldscenario**|**Is ATP Safe Links bescherming van toepassing in dit geval?**|
|:-----|:-----|
|Jean is lid van een groep met atp-beleid voor veilige koppelingen voor URL's in e-mail- en Office-documenten. Jean opent een PowerPoint-presentatie die iemand heeft verzonden en klikt vervolgens op een URL in de presentatie.|Ja. Het beleid voor veilige koppelingen van atp die is gedefinieerd, is van toepassing op jean's groep, Jean's e-mail en Word-, Excel-, PowerPoint- of Visio-documenten die Jean opent, zolang Jean is aangemeld en Microsoft 365-apps voor bedrijven op Windows-, iOS- of Android-apparaten is gebruikt.|
|In de organisatie van Chris hebben nog geen globale of beveiligingsbeheerders een ATP-beleid voor veilige koppelingen gedefinieerd. Chris ontvangt een e-mail met een URL naar een kwaadaardige website. Chris is zich niet bewust van de URL is kwaadaardig en klikt op de link.|Nee. Het standaardbeleid dat URL's voor iedereen in de organisatie dekt, moet worden gedefinieerd om bescherming te kunnen instellen.|
|In de organisatie van Pat hebben nog geen globale of beveiligingsbeheerders een ATP Safe Links-beleid gedefinieerd of bewerkt. Pat opent een Word-document en klikt op een URL in het bestand.|Nee. Een beleid dat Office-documenten bevat, moet worden gedefinieerd om bescherming te kunnen bieden. Zie [Beleid voor veilige koppelingen bij atp instellen in Office 365](set-up-atp-safe-links-policies.md).|
|Lee's organisatie heeft een ATP Safe Links beleid dat is `https://tailspintoys.com` vermeld als een geblokkeerde website. Lee ontvangt een e-mailbericht met een URL naar `https://tailspintoys.com/aboutus/trythispage` . Lee klikt op de URL.|Het hangt ervan af of de hele site en alle subpagina's zijn opgenomen in de lijst met geblokkeerde URL's. Zie [Een aangepaste lijst met geblokkeerde URL's instellen met ATP-veilige koppelingen](set-up-a-custom-blocked-urls-list-atp.md).|
|Jamie, Jean's collega, stuurt een e-mail naar Jean, niet wetende dat de e-mail een kwaadaardige URL bevat.|Het hangt af van de vraag of ATP Safe Links beleid zijn gedefinieerd voor e-mail verzonden binnen de organisatie. Zie [Beleid voor veilige koppelingen bij atp instellen in Office 365](set-up-atp-safe-links-policies.md).|
