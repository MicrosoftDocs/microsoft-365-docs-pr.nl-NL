---
title: Veilige bijlagen voor Office 365 ATP
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
description: De functie Veilige bijlagen biedt tijd-van-klikverificatie van e-mailbijlagen. Gebruik veilige bijlagen om uw organisatie te beschermen tegen schadelijke bestanden die mensen per e-mail verzenden of ontvangen.
ms.openlocfilehash: c95287b3dd05cce28bad6761ca7e69ce9cc2f914
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809854"
---
# <a name="office-365-atp-safe-attachments"></a>Veilige bijlagen voor Office 365 ATP

## <a name="overview-of-office-365-atp-safe-attachments"></a>Overzicht van veilige bijlagen voor Office 365 ATP

ATP Safe Attachments (samen met [ATP Safe Links)](atp-safe-links.md)maakt deel uit van [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). De functie VEILIG Bijlagen van ATP controleert of e-mailbijlagen schadelijk zijn en onderneemt vervolgens actie om uw organisatie te beschermen. De functie ATP Safe Attachments beschermt uw organisatie volgens [het ATP-beleid](set-up-atp-safe-attachments-policies.md) voor veilige bijlagen dat is ingesteld door uw globale Office 365- of beveiligingsbeheerders.

ATP-beveiliging kan ook worden uitgebreid naar bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams. Zie [Office 365 Advanced Threat Protection voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md)voor meer informatie.

## <a name="how-to-get-atp-safe-attachments"></a>Hoe krijg je ATP Safe Attachments

Zorg er eerst voor dat uw abonnement [geavanceerde bedreigingsbescherming](office-365-atp.md)bevat. ATP is opgenomen in abonnementen, zoals [Microsoft 365 E5,](https://www.microsoft.com/microsoft-365/enterprise/home) [Microsoft 365 Business,](https://www.microsoft.com/microsoft-365/business)Office 365 E5, Office 365 A5, enz. Als uw organisatie een Office 365-abonnement heeft dat office 365 ATP niet bevat, u ATP mogelijk als bijtelling aanschaffen. Zie [Office 365 Advanced Threat Protection-abonnementen en -prijzen](https://products.office.com/exchange/advance-threat-protection) en de beschrijving van de [Office 365 Advanced Threat Protection Service](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor meer informatie.

Controleer vervolgens of uw ATP-beleid voor veilige bijlagen is gedefinieerd. (Zie [Beleid voor veilig bijlagen voor Office 365 ATP instellen)](set-up-atp-safe-attachments-policies.md) De functies van ATP Safe Attachments zijn actief wanneer:

- Atp-beleid voor veilige bijlagen is ingesteld. (Zie [BELEID VOOR VEILIG DEELNEMEN AAN ATP instellen in Office 365](set-up-atp-safe-attachments-policies.md).)

- Gebruikers hebben zich aangemeld bij Office 365 met hun werk- of schoolaccount. (Zie [Aanmelden bij Office of Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)

Als u het ATP-beleid wilt definiëren (of bewerken), moet u een geschikte rol toegewezen krijgen. Enkele voorbeelden worden beschreven in de volgende tabel:

|Rol|Waar/hoe toegewezen|
|---------|---------|
|Globale beheerder van Office 365|De persoon die zich aanmeldt om Office 365 te kopen, is standaard een globale beheerder. (Zie [Informatie over office 365-beheerdersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.)|
|Beveiligingsbeheerder|Azure Active Directory-beheercentrum ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online Organisatiebeheer|Exchange-beheercentrum[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)( ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell))|

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Hoe te weten of ATP Safe Attachments bescherming is op zijn plaats

Nadat u [uw ATP Safe Attachments-beleid hebt gedefinieerd (of beoordeeld),](set-up-atp-safe-attachments-policies.md)is een goede manier om te zien hoe de service werkt door rapporten voor geavanceerde [bedreigingsbeveiliging](view-reports-for-atp.md)te bekijken.

In de volgende tabel worden enkele voorbeeldscenario's beschreven. In al deze gevallen gaan we ervan uit dat de organisatie een Office 365-abonnement heeft dat geavanceerde bedreigingsbeveiliging bevat.

|**Voorbeeldscenario**|**Is atp safe attachments bescherming van toepassing in dit geval?**|
|:-----|:-----|
|De organisatie van Pat heeft Office 365 E5, maar nog niemand heeft beleid voor ATP Safe Attachments gedefinieerd.|Nee. Hoewel de functie beschikbaar is, moet ten minste één ATP-beleid voor veilige bijlagen worden gedefinieerd om de bescherming van ATP Safe Attachments op zijn plaats te kunnen maken.|
|Lee is een medewerker op de verkoopafdeling van Contoso. Lee's organisatie heeft een ATP Safe Attachments beleid dat alleen van toepassing is op financiële werknemers.|Nee. In dit geval zouden financiële werknemers ATP Safe Attachments-bescherming hebben, maar andere werknemers, waaronder de verkoopafdeling, zouden dat pas doen totdat beleid is gedefinieerd dat deze groepen bevat.|
|Gisteren heeft een Office 365-beheerder van de organisatie van Jean een ATP Safe Attachments-beleid ingesteld dat van toepassing is op alle werknemers. Eerder vandaag ontving Jean een e-mailbericht met een bijlage.|Ja. In dit voorbeeld heeft Jean een licentie voor Advanced Threat Protection en is een ATP Safe Attachments-beleid dat Jean omvat gedefinieerd. Het duurt meestal ongeveer 30 minuten voordat een nieuw beleid van kracht wordt in datacenters; aangezien in dit geval een dag is verstreken, moet het beleid van kracht zijn.|
|Chris's organisatie heeft Office 365 E5 met ATP Safe Attachments-beleid voor iedereen in de organisatie. Chris ontvangt een e-mail met een bijlage en stuurt het bericht door naar anderen die zich buiten de organisatie bevinden.|ATP Safe Attachments bescherming is op zijn plaats voor berichten die Chris ontvangt. Als de organisaties van de ontvangers ook een ATP-beleid voor veilige bijlagen hebben, wordt het bericht dat Chris doorstuurt onderworpen aan dit beleid wanneer het doorgestuurde bericht binnenkomt.|
|Jamie's organisatie heeft atp-beleid voor veilige bijlagen en [ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md) is ingeschakeld. Jamie gaat ervan uit dat elk bestand in SharePoint Online is gescand en veilig is om te openen of te downloaden.|ATP Safe Attachments bescherming is op zijn plaats volgens het beleid dat zijn gedefinieerd; Dit betekent echter niet dat elk bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams wordt gescand. (Zie [ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md)voor meer informatie.)|

## <a name="submitting-files-for-malware-analysis"></a>Bestanden indienen voor malwareanalyse

- Als u een bestand ontvangt dat u Microsoft wilt vragen te analyseren, gaat u naar [Een bestand indienen voor malwareanalyse.](https://aka.ms/wdsi/submit)

- Als u een e-mailbericht (met of zonder bijlage) ontvangt dat u voor analyse aan Microsoft wilt indienen, gebruikt u de [invoegtoepassing Rapportbericht](enable-the-report-message-add-in.md).
