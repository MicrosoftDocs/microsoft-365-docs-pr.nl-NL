---
title: Teams met basisbescherming configureren
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Leer teams met een basisbescherming te implementeren.
ms.openlocfilehash: 4f38bf286b8ebd3edf6f7705299008566d2b7c8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916332"
---
# <a name="configure-teams-with-baseline-protection"></a>Teams met basisbescherming configureren

In dit artikel leest u hoe u teams met een basisbescherming kunt implementeren. Gebruikers kunnen bij een basisbescherming een groot aantal opties voor samenwerking gebruiken terwijl het beheer van machtigingen wordt verbeterd en er beveiliging tegen te veel delen wordt geboden. Aanbevolen beveiliging voor de basisbescherming bestaat onder andere uit beleidsregels voor apparaattoegang en beveiliging tegen malware. Daarnaast kunt u eventueel beleid voor voorwaardelijke toegang en bescherming tegen gegevensverlies toepassen.

## <a name="initial-protections"></a>Initiële bescherming

Als eerste stap wordt u aangeraden basisbeleid voor identiteiten en apparaattoegang te configureren. Zie [Beleidsaanbevelingen voor het beveiligen van Teams-chats, -groepen en -bestanden](../security/office-365-security/teams-access-policies.md) voor meer informatie.

We raden u ook aan de basisfuncties van Defender voor Office 365 in te schakelen voor de bescherming tegen malware in documenten, bijlagen en koppelingen. We adviseren u om de opties in de volgende tabel in te schakelen.

|Optie|Informatie|
|:------|:-----------|
|Veilige bijlagen voor SPO, OneDrive en Teams|[Veilige bijlagen](../security/office-365-security/atp-safe-attachments.md)<br>[Defender voor Office 365 - SharePoint, OneDrive en Microsoft Teams](../security/office-365-security/atp-for-spo-odb-and-teams.md)|
|Veilige documenten|[Veilige documenten in Microsoft Defender voor Office 365](../security/office-365-security/safe-docs.md)|
|Veilige koppelingen voor Teams|[Veilige Office 365-koppelingen in Teams](../security/office-365-security/atp-safe-links.md#safe-links-settings-for-microsoft-teamssafe-links-settings-for-microsoft-teams)<br>[Veilige koppelingen](../security/office-365-security/atp-safe-links.md)|

## <a name="teams-guest-sharing"></a>Delen met gasten in Teams

In elk van de lagen kan er worden gedeeld met personen buiten uw organisatie. Voor de gevoelige en zeer gevoelige lagen kan het delen met gasten worden uitgeschakeld op teamniveau door gevoeligheidslabels te gebruiken. Maar de instelling voor het delen met gasten op organisatieniveau moet zijn ingeschakeld om het delen met gasten in Teams te kunnen laten werken.

![Schermafbeelding van wisselknop Gasttoegang in Teams](../media/teams-guest-access-toggle-on.png)

Instellingen voor gasttoegang in Teams instellen

1. Meld u aan bij het Microsoft 365-beheercentrum op [https://admin.microsoft.com](https://admin.microsoft.com).
2. Klik in het navigatievenster aan de linkerkant op **Alles weergeven**.
3. Klik onder **Beheercentra** op **Teams**.
4. Vouw in het Teams-beheercentrum in het linkernavigatievenster **Instellingen voor hele organisatie** uit en klik vervolgens op **Gasttoegang**.
5. Zorg ervoor dat **Gasttoegang in Teams toestaan** is ingesteld op **Aan**.
6. Breng de gewenste wijzigingen aan in de extra gastinstellingen en klik vervolgens op **Opslaan**.

> [!NOTE]
> Het kan 24 uur duren voordat de instelling voor gasten in Teams actief wordt nadat u deze hebt ingeschakeld.

Delen met gasten is standaard ingeschakeld voor Office 365-groepen en SharePoint, maar als u eerder een van de instellingen voor het delen met gasten hebt gewijzigd voor uw organisatie, wordt u aangeraden [Samenwerken met gasten in een team](./collaborate-as-team.md) te controleren om ervoor te zorgen dat de functie voor het delen met gasten beschikbaar is in Teams.

## <a name="site-and-file-sharing"></a>Sites en bestanden delen

Als u het risico van het onbedoeld delen van bestanden of mappen met personen buiten uw organisatie wilt beperken, kunt u het beste de standaardkoppeling voor delen voor SharePoint wijzigen in *Alleen personen in uw organisatie*. (Als gebruikers extern moeten kunnen delen en u het delen met gasten hebt ingeschakeld, kunnen ze het koppelingstype nog steeds wijzigen wanneer ze delen.)

De standaardkoppeling voor delen wijzigen
1. Open het [SharePoint-beheercentrum](https://admin.microsoft.com/sharepoint).
2. Klik onder **Beleid** op **Delen**.
3. Selecteer onder **Koppelingen naar bestanden en mappen** de optie **Alleen personen binnen uw organisatie**.
4. Klik op **Opslaan**.

Voor de beste ervaring voor het delen met gasten wordt u ook aangeraden om [SharePoint- en OneDrive-integratie met Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) in te schakelen.

## <a name="create-a-team"></a>Een team maken

Er wordt een extra configuratie uitgevoerd voor de basisbescherming in de SharePoint-site die is gekoppeld aan een team. [Maak een openbaar of persoonlijk team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) voordat u verder gaat met de volgende sectie.

## <a name="site-sharing-settings"></a>Instellingen voor het delen van een site

Leden van een SharePoint-site kunnen standaard anderen uitnodigen voor de site. Wanneer een site deel uitmaakt van een team, worden teamleden opgenomen als siteleden. Personen die rechtstreeks aan de site worden toegevoegd, hebben echter geen toegang tot de rest van het team. Om deze reden wordt u aangeraden machtigingen uitsluitend te beheren via het team.

Om u te helpen bij het beheer van machtigingen wordt u aangeraden de bijbehorende site zo te configureren dat alleen eigenaren zelf de site mogen delen. Dit vereenvoudigt het beheer van machtigingen en helpt voorkomen dat anderen toegang krijgen zonder dat de eigenaar hiervan op de hoogte is. Doe dit voor elk team waarvoor basisbescherming is vereist.

De instellingen voor het delen van een site bijwerken
1. Klik op de werkbalk van het team op **Bestanden**.
2. Klik op **Openen in SharePoint**.
3. Klik op de werkbalk van de SharePoint-site op het pictogram Instellingen en vervolgens op **Sitemachtigingen**.
4. Klik in het deelvenster **Site-machtigingen** onder **Delen van een site** op **Wijzigen hoe leden kunnen delen**.
5. Selecteer onder **Machtigingen voor delen** de optie **Site-eigenaren en leden, en personen met machtigingen voor bewerken kunnen bestanden en mappen delen, maar alleen site-eigenaren kunnen de site delen** en klik vervolgens op **Opslaan**.

## <a name="additional-protections"></a>Aanvullende beveiligingsmaatregelen

Microsoft 365 biedt aanvullende methoden voor het beveiligen van uw inhoud. Overweeg of de volgende opties de beveiliging van uw organisatie zouden kunnen verbeteren.

- Laat uw gastgebruikers akkoord gaan met de [gebruiksrechtenovereenkomst](/azure/active-directory/conditional-access/terms-of-use).
- Configureer een [beleid voor de time-out van een sessie](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) voor gasten.
- Maak [typen voor gevoelige informatie](../compliance/sensitive-information-type-learn-about.md) en gebruik [gegevensverliesbeveiliging](../compliance/data-loss-prevention-policies.md) om beleid in te stellen rond toegang tot gevoelige informatie.

## <a name="see-also"></a>Zie ook

[Vergaderingsbeleid beheren in Teams](/microsoftteams/meeting-policies-in-teams)

[Aan de slag met insider-risicobeheer](../compliance/insider-risk-management-configure.md)