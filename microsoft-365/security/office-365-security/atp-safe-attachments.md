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
description: In dit artikel leest u meer over de functie VEILIGE bijlagen atp voor Office 365 en hoe u de functie voor uw abonnement krijgen.
ms.openlocfilehash: 77842596b460e2d96ccde79e9c8c6ef3d1f8985a
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754758"
---
# <a name="atp-safe-attachments"></a>ATP-veilige bijlagen

## <a name="overview-of-office-365-atp-safe-attachments"></a>Overzicht van veilige Office 365-atp-bijlagen

ATP Safe Attachments (samen met [ATP Safe Links)](atp-safe-links.md)is onderdeel van [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). De functie Veilige bijlagen atp controleert of e-mailbijlagen schadelijk zijn en onderneemt vervolgens actie om uw organisatie te beschermen. De functie VEILIGE ATP-bijlagen beschermt uw organisatie volgens [het ATP Safe Attachments-beleid](set-up-atp-safe-attachments-policies.md) dat is ingesteld door uw wereldwijde of beveiligingsbeheerders.

ATP-beveiliging kan ook worden uitgebreid naar bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams. Zie [Geavanceerde bedreigingsbeveiliging van Office 365 voor SharePoint, OneDrive en Microsoft Teams voor](atp-for-spo-odb-and-teams.md)meer informatie.

## <a name="how-to-get-atp-safe-attachments"></a>Hoe atp-veilige bijlagen te krijgen

Zorg er eerst voor dat uw abonnement [Geavanceerde bedreigingsbescherming](office-365-atp.md)bevat. ATP is opgenomen in abonnementen, zoals [Microsoft 365 E5,](https://www.microsoft.com/microsoft-365/enterprise/home) [Microsoft 365 Business Premium,](https://www.microsoft.com/microsoft-365/business)Office 365 E5, Office 365 A5, enz. Als uw organisatie een Microsoft 365-abonnement heeft dat geen Office 365 ATP bevat, u atp mogelijk als add-on aanschaffen. Zie [Office 365 Advanced Threat Protection-abonnementen en -prijzen en](https://products.office.com/exchange/advance-threat-protection) de beschrijving van de [Geavanceerde bedreigingsbeveiliging van Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor geavanceerde bedreigingenservice voor meer informatie.

Zorg er vervolgens voor dat uw ATP-beleid voor veilige bijlagen is gedefinieerd. (Zie [Beleid voor office 365 ATP-veilige bijlagen instellen)](set-up-atp-safe-attachments-policies.md) ATP Safe Attachments-functies zijn actief wanneer:

- Atp Safe Attachments-beleid is ingesteld. (Zie [Atp-beleid voor veilige bijlagen instellen in Office 365](set-up-atp-safe-attachments-policies.md).)

- Gebruikers hebben zich aangemeld met hun werk- of schoolaccount. (Zie [Aanmelden bij Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).)

Als u ATP-beleid wilt definiëren (of bewerken), moet u een geschikte rol toegewezen krijgen. Enkele voorbeelden worden beschreven in de volgende tabel:

|Rol|Waar/hoe toegewezen|
|---------|---------|
|globale beheerder|De persoon die zich aanmeldt om Microsoft 365 te kopen, is standaard een globale beheerder. (Zie [Over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)|
|Beveiligingsbeheerder|Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Exchange Online Organisatiebeheer|Exchange-beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Hoe weet u of atp-beveiliging voor veilige bijlagen aanwezig is

Nadat u [uw ATP Safe Attachments-beleid hebt gedefinieerd (of beoordeeld),](set-up-atp-safe-attachments-policies.md)is een goede manier om te zien hoe de service werkt door rapporten voor Geavanceerde [bedreigingsbescherming te bekijken.](view-reports-for-atp.md)

In de volgende tabel worden enkele voorbeeldscenario's beschreven. In al deze gevallen gaan we ervan uit dat de organisatie een Microsoft 365-abonnement heeft dat Advanced Threat Protection bevat.

|**Voorbeeldscenario**|**Is ATP Safe Attachments bescherming van toepassing in dit geval?**|
|:-----|:-----|
|Pat's organisatie heeft Office 365 E5, maar niemand heeft nog beleid gedefinieerd voor ATP Safe Attachments.|Nee. Hoewel de functie beschikbaar is, moet ten minste één ATP Safe Attachments-beleid worden gedefinieerd om de bescherming van ATP Safe Attachments op zijn plaats te krijgen.|
|Lee is een medewerker op de verkoopafdeling van Contoso. Lee's organisatie heeft een ATP Safe Attachments beleid in de plaats die alleen van toepassing is op de financiering van werknemers.|Nee. In dit geval zouden financiële werknemers bescherming hebben voor ATP Safe Attachments, maar andere werknemers, waaronder de verkoopafdeling, pas als beleid met deze groepen is gedefinieerd.|
|Gisteren heeft een beheerder van Jean's organisatie een ATP Safe Attachments-beleid ingesteld dat van toepassing is op alle werknemers. Eerder vandaag ontving Jean een e-mailbericht met een bijlage.|Ja. In dit voorbeeld heeft Jean een licentie voor Geavanceerde bedreigingsbescherming en is een ATP-beleid voor veilige bijlagen met Jean gedefinieerd. Het duurt meestal ongeveer 30 minuten voordat een nieuw beleid van kracht wordt in verschillende datacenters; aangezien in dit geval een dag is verstreken, moet het beleid van kracht zijn.|
|De organisatie van Chris heeft Office 365 E5 met ATP Safe Attachments-beleid voor iedereen in de organisatie. Chris ontvangt een e-mail met een bijlage en stuurt het bericht door naar anderen die zich buiten de organisatie bevinden.|ATP Safe Attachments bescherming is op zijn plaats voor berichten die Chris ontvangt. Als de organisaties van de ontvangers ook atp-beleid voor veilige bijlagen hebben, is het bericht dat Chris doorstuurt onderworpen aan dit beleid wanneer het doorgestuurde bericht binnenkomt.|
|Jamie's organisatie heeft ATP Safe Attachments-beleid en [ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md) is ingeschakeld. Jamie gaat ervan uit dat elk bestand in SharePoint Online is gescand en veilig is om te openen of te downloaden.|Atp Safe Attachments bescherming is van kracht volgens het beleid dat zijn gedefinieerd; Dit betekent echter niet dat elk bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams wordt gescand. (Zie [ATP voor SharePoint, OneDrive en Microsoft Teams voor](atp-for-spo-odb-and-teams.md)meer informatie .)|

## <a name="submitting-files-for-malware-analysis"></a>Bestanden indienen voor malware-analyse

- Als u een bestand ontvangt dat u Microsoft wilt vragen te analyseren, gaat u naar [Een bestand indienen voor malware-analyse.](https://aka.ms/wdsi/submit)

- Als u een e-mailbericht ontvangt (met of zonder bijlage) dat u voor analyse bij Microsoft wilt indienen, [raadpleegt](report-junk-email-messages-to-microsoft.md)u Berichten en bestanden rapporteren aan Microsoft .
