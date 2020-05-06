---
title: ATP-veilige bijlagen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over de functie Veilige bijlagen atp voor Office 365 en hoe u de functie voor uw abonnement downloaden.
ms.openlocfilehash: e6cbd5cb494e765bdb849da93114ea4168ab3c93
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034850"
---
# <a name="atp-safe-attachments"></a>ATP-veilige bijlagen

## <a name="overview-of-office-365-atp-safe-attachments"></a>Overzicht van veilige bijlagen bij Office 365 ATP

ATP Safe Attachments (samen met [ATP Safe Links)](atp-safe-links.md)maakt deel uit van [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). De functie ATP-veilige bijlagen controleert of e-mailbijlagen schadelijk zijn en onderneemt vervolgens actie om uw organisatie te beschermen. De functie VEILIGE bijlagen atp beschermt uw organisatie volgens [het beleid voor veilige bijlagen van ATP](set-up-atp-safe-attachments-policies.md) dat is ingesteld door uw wereldwijde of beveiligingsbeheerders.

ATP-beveiliging kan ook worden uitgebreid naar bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams. Zie [Geavanceerde bedreigingsbeveiliging van Office 365 voor SharePoint, OneDrive en Microsoft Teams voor](atp-for-spo-odb-and-teams.md)meer informatie.

## <a name="how-to-get-atp-safe-attachments"></a>Hoe ontvang je ATP Safe Attachments

Controleer eerst of uw abonnement [advanced threat protection](office-365-atp.md)bevat. ATP is opgenomen in abonnementen, zoals [Microsoft 365 E5,](https://www.microsoft.com/microsoft-365/enterprise/home) [Microsoft 365 Business Premium,](https://www.microsoft.com/microsoft-365/business)Office 365 E5, Office 365 A5, enz. Als uw organisatie een Microsoft 365-abonnement heeft dat geen Office 365 ATP bevat, u mogelijk ATP als add-on aanschaffen. Zie [office 365 Advanced Threat Protection-abonnementen en -prijzen en](https://products.office.com/exchange/advance-threat-protection) de [office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor meer informatie.

Controleer vervolgens of uw beleid voor veilige bijlagen atp is gedefinieerd. (Zie Beleid voor [veilige bijlagen van Office 365 instellen)](set-up-atp-safe-attachments-policies.md) Functies voor veilige bijlagen van ATP zijn actief wanneer:

- Het beleid voor veilige bijlagen van ATP is ingesteld. (Zie Beleid voor [veilige bijlagen van ATP instellen in Office 365](set-up-atp-safe-attachments-policies.md).)

- Gebruikers hebben zich aangemeld met hun werk- of schoolaccount. (Zie [Aanmelden bij Office of Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)

Als u ATP-beleid wilt definiëren (of bewerken), moet u een geschikte rol toegewezen krijgen. Enkele voorbeelden worden beschreven in de volgende tabel:

|Rol|Waar/hoe toegewezen|
|---------|---------|
|globale beheerder|De persoon die zich aanmeldt om Microsoft 365 te kopen is standaard een globale beheerder. (Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)|
|Beveiligingsbeheerder|Azure Active Directory-beheercentrum ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online Organisatiebeheer|Exchange-beheercentrum[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)( ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell)](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Hoe weet u of de bescherming van ATP-veilige bijlagen aanwezig is

Nadat u [uw ATP-beleid voor veilige bijlagen hebt gedefinieerd (of beoordeeld),](set-up-atp-safe-attachments-policies.md)u een goede manier om te zien hoe de service werkt door rapporten voor Geavanceerde [bedreigingsbeveiliging te bekijken](view-reports-for-atp.md).

In de volgende tabel worden enkele voorbeeldscenario's beschreven. In al deze gevallen gaan we ervan uit dat de organisatie een Microsoft 365-abonnement heeft dat Advanced Threat Protection bevat.

|**Voorbeeldscenario**|**Is atp-bescherming voor veilige bijlagen in dit geval van toepassing?**|
|:-----|:-----|
|Pat's organisatie heeft Office 365 E5, maar niemand heeft nog geen beleid voor ATP Safe Attachments gedefinieerd.|Nee. Hoewel de functie beschikbaar is, moet ten minste één ATP-beleid voor veilige bijlagen worden gedefinieerd om de bescherming van ATP-veilige bijlagen te kunnen gebruiken.|
|Lee is een medewerker op de verkoopafdeling van Contoso. Lee's organisatie heeft een ATP Safe Attachments-beleid dat alleen van toepassing is op financiële medewerkers.|Nee. In dit geval zouden financiële medewerkers bescherming hebben tegen ATP Safe Attachments, maar andere werknemers, waaronder de verkoopafdeling, zouden dat pas doen als beleid dat deze groepen omvat, is gedefinieerd.|
|Gisteren heeft een beheerder van Jean's organisatie een ATP Safe Attachments-beleid ingesteld dat van toepassing is op alle werknemers. Eerder vandaag ontving Jean een e-mailbericht met een bijlage.|Ja. In dit voorbeeld heeft Jean een licentie voor Geavanceerde bedreigingsbeveiliging en is een ATP-beleid voor veilige bijlagen dat Jean bevat gedefinieerd. Het duurt meestal ongeveer 30 minuten voordat een nieuw beleid van kracht wordt in alle datacenters; aangezien er in dit geval een dag is verstreken, moet het beleid van kracht zijn.|
|Chris's organisatie heeft Office 365 E5 met ATP Safe Attachments-beleid voor iedereen in de organisatie. Chris ontvangt een e-mail met een bijlage en stuurt het bericht door naar anderen die zich buiten de organisatie bevinden.|ATP Safe Attachments bescherming is aanwezig voor berichten die Chris ontvangt. Als de organisaties van de ontvangers ook een beleid voor veilige bijlagen voor ATP hebben, is het bericht dat Chris doorstuurt onderworpen aan dat beleid wanneer het doorgestuurde bericht binnenkomt.|
|Jamie's organisatie heeft atp-beleid voor veilige bijlagen en [ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md) is ingeschakeld. Jamie gaat ervan uit dat elk bestand in SharePoint Online is gescand en veilig is om te openen of te downloaden.|Atp Safe Attachments bescherming is op zijn plaats volgens het beleid dat is gedefinieerd; Dit betekent echter niet dat elk bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams wordt gescand. (Zie [ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md)voor meer informatie.)|

## <a name="submitting-files-for-malware-analysis"></a>Bestanden indienen voor malware-analyse

- Als u een bestand ontvangt dat u Microsoft wilt vragen te analyseren, gaat u [naar Een bestand indienen voor malware-analyse.](https://aka.ms/wdsi/submit)

- Zie [Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)als u een e-mailbericht (met of zonder bijlage) ontvangt dat u ter analyse aan Microsoft wilt indienen.
