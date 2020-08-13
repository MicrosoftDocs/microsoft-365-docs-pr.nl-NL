---
title: Veilige bijlage van ATP
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
description: In dit artikel vindt u meer informatie over de functie voor het beveiligen van de ATP voor Office 365 en over hoe u de functie voor uw abonnement kunt krijgen.
ms.openlocfilehash: 16b9ae47ead318e200cdf1e5e5beb58c2bc396bc
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656991"
---
# <a name="atp-safe-attachments"></a>Veilige bijlage van ATP

## <a name="overview-of-office-365-atp-safe-attachments"></a>Overzicht van veilige bijlagen van Office 365

Veilige bijlage van ATP (samen met [veilige koppelingen voor ATP](atp-safe-links.md)) maakt deel uit van [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP). Met de functie voor het veilig maken van een ATP-bijlage controleert u of e-mailbijlagen schadelijk zijn en gaat u vervolgens actie ondernemen om uw organisatie te beveiligen. Met de functie voor het veilig maken van een ATP beschermt u uw organisatie op basis van het [beleid voor veilige bijlagen](set-up-atp-safe-attachments-policies.md) voor de gebruikers die zijn ingesteld door uw globale beheerder of beveiligingsbeheerder.

ATP-beveiliging kan ook worden uitgebreid met bestanden in SharePoint Online, OneDrive voor bedrijven en Microsoft teams. Zie [Office 365 Advanced Threat Protection voor SharePoint, OneDrive en Microsoft teams voor](atp-for-spo-odb-and-teams.md)meer informatie.

## <a name="how-to-get-atp-safe-attachments"></a>Hoe kan ik veilige bijlagen voor ATP weergeven?

Zorg er eerst voor dat uw abonnement [Advanced Threat Protection](office-365-atp.md)omvat. ATP is inbegrepen in abonnementen, zoals [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business Premium](https://www.microsoft.com/microsoft-365/business), Office 365 E5, Office 365 A5, etc. Als uw organisatie een Microsoft 365-abonnement heeft dat geen Office 365-ATP bevat, kunt u ATP kopen als een invoegtoepassing. Zie voor meer informatie [office 365 Advanced Threat Protection-abonnementen en-prijzen](https://products.office.com/exchange/advance-threat-protection) en de beschrijving van de [Office 365 Advanced Threat Protection-Service](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Zorg er vervolgens voor dat u beleidsregels voor veilige bijlagen voor ATP definieert. (Zie [beleidsregels voor veilige bijlagen van Office 365 instellen](set-up-atp-safe-attachments-policies.md)) Functies voor het veilig maken van een vrije bijlage zijn in de volgende gevallen actief:

- Beleidsregels voor veilige bijlagen met ATP zijn ingesteld. (Zie [beleidsregels voor het instellen van vrije bijlagen in Office 365](set-up-atp-safe-attachments-policies.md).)

- Gebruikers hebben zich aangemeld met hun werk-of schoolaccount. (Zie [Aanmelden bij Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).)

Als u ATP-beleidsregels wilt definiëren (of bewerken), moet aan u de juiste rol zijn toegewezen. In de volgende tabel worden enkele voorbeelden beschreven:

|Rol|Where/hoe toegewezen|
|---|---|
|globale beheerder|De persoon die zich registreert voor het kopen van Microsoft 365 is standaard een globale beheerder. (Zie [informatie over Microsoft 365-beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.)|
|Beveiligingsbeheerder|Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Beheer van organisatie van Exchange Online|Exchange-Beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>of <br>  PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Hoe weet u of de beveiliging van de ATP-beveiliging op hun plaats is.

Nadat u [uw beleid voor veilige bijlagen van ATP hebt gedefinieerd (of gecontroleerd)](set-up-atp-safe-attachments-policies.md), is een goede manier om te zien hoe de service werkt door [rapporten te bekijken voor Advanced Threat Protection](view-reports-for-atp.md).

In de volgende tabel ziet u enkele voorbeelden van scenario's. In al deze gevallen wordt ervan uitgegaan dat de organisatie een Microsoft 365-abonnement heeft met Advanced Threat Protection.

****

|Voorbeeld van scenario|Is er sprake van een veilige beveiliging van de bijlage.|
|---|---|
|De organisatie van de Pat heeft Office 365 E5, maar niemand heeft hiervoor beleidsregels ingesteld voor het veilig ontvangen van ATP.|Nee. Hoewel de functie beschikbaar is, moet ten minste één beveiligingsbeleid voor de ATP-versie van het bestand worden gedefinieerd, zodat de bescherming van de beveiliging van ATP veilig is.|
|Lee is een werknemer in de verkoopafdeling bij contoso. De organisatie van Lee beschikt over een veilig bijlage beleid voor de financiering van de werknemers van Lee.|Nee. In dit geval waren de werknemers voor de financiering van de werknemers de bescherming voor veilige bijlagen nodig, maar andere werknemers, waaronder de verkoopafdeling, zouden niet tot het beleid van deze groepen behoren.|
|Gisteren, een beheerder van de organisatie van Jean, een voorbeeld van een ATP-toepassing instellen die van toepassing is op alle werknemers. Vervolgens heeft Jean een e-mailbericht ontvangen met een bijlage.|Ja. In dit voorbeeld heeft Jean een licentie voor Advanced Threat Protection en een beleid voor veilige bijlagen met de functie Jean is gedefinieerd. Het duurt doorgaans ongeveer dertig minuten voordat een nieuw beleid is doorgevoerd in de datacenters; Aangezien een dag in dit geval is verstreken, moet het beleid van kracht zijn.|
|De organisatie van Chris heeft Office 365 E5 met een voor iedereen in de organisatie. Chris ontvangt een e-mailbericht met een bijlage en stuurt het bericht door naar anderen buiten de organisatie.|Beveiliging van ATP voor veilige bijlagen is de bescherming van berichten die Chris ontvangt. Als de organisaties van de geadresseerden ook hun beleidsregels voor veilige bijlagen voor ATP hebben, is het bericht dat Chris forwarding onderhevig is aan die beleidsregels wanneer het doorgestuurde bericht binnenkomt.|
|De organisatie van Janny heeft een goedgekeurd beleid voor het opslaan van bijlagen en [ATP voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md) ingeschakeld. Jan gaat ervan uit dat elk bestand in SharePoint Online is gescand en dat het veilig kan worden geopend of gedownload.|De bescherming van documenten in de vrije ruimte op basis van de gedefinieerde beleidsregels; Dit houdt in dat u echter niet elk afzonderlijk bestand in SharePoint Online, OneDrive voor bedrijven of Microsoft teams scant. (Zie [ATP voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md)voor meer informatie.)|
|

## <a name="submitting-files-for-malware-analysis"></a>Bestanden voor de analyse van malware indienen

- Als u een bestand ontvangt dat u wilt laten weten dat Microsoft dit wil analyseren, raadpleegt u [een bestand indienen voor het analyseren van schadelijke software](https://aka.ms/wdsi/submit).

- Als u een e-mailbericht ontvangt (met of zonder bijlage) dat u bij Microsoft wilt indienen voor analyse, raadpleegt u [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).
