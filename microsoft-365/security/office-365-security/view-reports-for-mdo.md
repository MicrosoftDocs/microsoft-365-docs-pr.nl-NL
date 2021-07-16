---
title: Defender voor Office 365-rapporten weergeven
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen leren hoe ze de Defender kunnen vinden en gebruiken voor Office 365 rapporten die beschikbaar zijn in de Microsoft 365 Defender portal.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8bb03202139137adf55c4c10230b1c4e99253ba
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454719"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a>Defender weergeven voor Office 365 rapporten in de Microsoft 365 Defender portal

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender voor Office 365-organisaties (bijvoorbeeld Microsoft 365 E5-abonnementen of Microsoft Defender voor Office 365 Plan 1 of Microsoft Defender voor Office 365 Abonnement 2-invoegtoepassingen) bevatten diverse beveiligingsgerelateerde rapporten. Als u de [benodigde](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)machtigingen hebt, kunt u deze rapporten  bekijken in de Microsoft 365 Defender-portal door naar Rapporten e-mail & samenwerking e-mail & \>  \> **samenwerkingsrapporten.** Als u rechtstreeks naar de pagina **E-mail & samenwerkingsrapporten** wilt gaan, opent u <https://security.microsoft.com/emailandcollabreport> .

![Pagina & samenwerkingsrapporten in de Microsoft 365 Defender portal](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> E-mailbeveiligingsrapporten waarvoor Defender niet nodig is Office 365 worden beschreven in E-mailbeveiligingsrapporten [weergeven in de Microsoft 365 Defender portal.](view-email-security-reports.md)
>
> Rapporten die zijn gerelateerd aan de e-mailstroom, zijn nu in het Exchange beheercentrum (EAC). Zie E-mailstroomrapporten in het nieuwe Exchange [beheercentrum voor meer informatie over deze rapporten.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)

## <a name="safe-attachments-file-types-report"></a>Safe Rapport Bestandstypen bijlagen

> [!NOTE]
> Het **Safe bestandstypen van** bijlagen wordt uiteindelijk verwijderd. Dezelfde informatie is beschikbaar in het rapport [Bedreigingsbeveiligingsstatus.](#threat-protection-status-report)

## <a name="safe-attachments-message-disposition-report"></a>Safe Berichtbezettingsrapport bijlagen

> [!NOTE]
> Het **Safe berichtbezettingsrapport** bijlagen wordt uiteindelijk verwijderd. Dezelfde informatie is beschikbaar in het rapport [Bedreigingsbeveiligingsstatus.](#threat-protection-status-report)

## <a name="mail-latency-report"></a>E-maillatentierapport

In **het rapport E-maillatentie** ziet u een statistische weergave van de latentie van e-mailbezorging en detonatie binnen uw organisatie. E-mailbezorgingstijden in de service worden beïnvloed door een aantal factoren en de absolute levertijd in seconden is vaak geen goede indicator voor succes of een probleem. Een trage levertijd op één dag kan worden beschouwd als een gemiddelde levertijd op een andere dag, of omgekeerd. Hiermee wordt geprobeerd berichtbezorging te kwalificeren op basis van statistische gegevens over de waargenomen levertijden van andere berichten.

Clientzijde en netwerklatentie zijn niet inbegrepen.

Als u het rapport wilt bekijken, opent  [u de Microsoft 365 Defender portal](https://security.microsoft.com), gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**. Zoek op **de pagina & e-mailsamenwerkingsrapporten** naar **het rapport E-maillatentie** en klik vervolgens op **Details weergeven.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/mailLatencyReport> .

![Rapportwidget e-maillatentie op de pagina E-mail & samenwerkingsrapporten](../../media/mail-latency-report-widget.png)

Op de **pagina E-maillatentierapport** zijn de volgende tabbladen beschikbaar op de pagina **E-maillatentierapport:**

- **50e percentiel:** dit is het midden voor bezorgingstijden van berichten. U kunt deze waarde beschouwen als een gemiddelde levertijd. Dit tabblad is standaard geselecteerd.
- **90e percentiel:** dit geeft een hoge latentie voor berichtbezorging aan. Slechts 10% van de berichten duurde langer dan deze waarde.
- **99e percentiel:** dit geeft de hoogste latentie voor berichtbezorging aan.

Ongeacht het tabblad dat u selecteert, worden in de grafiek berichten weergegeven die zijn ingedeeld in de volgende categorieën:

- **Latentie voor e-mailbezorging**
- **Detonaties**

Wanneer u de muisaanwijzer boven een categorie in de grafiek beweegt, ziet u een uitsplitsing van de latentie in elke categorie.

![50e percentielweergave van het rapport E-maillatentie](../../media/mail-latency-report-50th-percentile-view.png)

Als u op **Filter** klikt, kunt u zowel de grafiek als de detailtabel filteren op de volgende waarden:

- **Datum (UTC)**: **Begindatum** en **einddatum**
- **Berichtweergave:** Een van de volgende waarden:
  - **Alle berichten**
  - **Berichten met bijlagen of URL's**
  - **Ontplofte berichten**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:

- **Datum (UTC)**
- **Percentielen:** **50,** **90** of **99**
- **Aantal berichten**
- **Algehele latentie**

## <a name="threat-protection-status-report"></a>Statusrapport bedreigingsbeveiliging

Het rapport Status **van** bedreigingsbeveiliging is één weergave waarin informatie wordt bijeengehouden over schadelijke inhoud en schadelijke e-mail die is gedetecteerd en geblokkeerd door [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) en Microsoft Defender voor Office 365. Zie Rapport [bedreigingsbeveiligingsstatus voor](view-email-security-reports.md#threat-protection-status-report)meer informatie.

## <a name="url-threat-protection-report"></a>URL-bedreigingsbeveiligingsrapport

Het **rapport URL-bedreigingsbeveiliging** bevat overzichts- en trendweergaven voor gedetecteerde bedreigingen en acties die zijn ondernomen op URL-klikken als onderdeel [van Safe Koppelingen.](safe-links.md) In dit rapport zijn geen klikgegevens van gebruikers waar Safe beleid voor koppelingen is toegepast, is de optie **Gebruikersklikken** niet bijhouden geselecteerd.

Als u het rapport wilt bekijken, opent  [u de Microsoft 365 Defender portal](https://security.microsoft.com), gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**. Zoek op **de pagina & samenwerkingsrapporten** naar **de pagina URL-beveiliging** en klik vervolgens op **Details weergeven.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/URLProtectionActionReport> .

![Widget urlbeveiligingsrapport op de pagina E-mail & samenwerkingsrapporten](../../media/url-protection-report-widget.png)

De beschikbare weergaven op de **rapportpagina VOOR URL-bedreigingsbeveiliging** worden in de volgende secties beschreven.

> [!NOTE]
> Dit is een *beveiligingstrendrapport, wat* betekent dat gegevens trends vertegenwoordigen in een grotere gegevensset. Hierdoor zijn de gegevens in de grafieken hier niet in realtime beschikbaar, maar de gegevens in de detailtabel wel, zodat er mogelijk een kleine afwijking tussen de twee wordt gezien. De grafieken worden eenmaal per vier uur vernieuwd en bevatten gegevens voor de afgelopen 90 dagen.

### <a name="view-data-by-url-click-protection-action"></a>Gegevens weergeven op URL klik op beveiligingsactie

![URL klik op beveiligingsactieweergave in het rapport URL-bedreigingsbeveiliging](../../media/url-threat-protection-report-url-click-protection-action-view.png)

In **de weergave Gegevens per URL klikken op beveiligingsactieweergave** ziet u het aantal URL-klikken van gebruikers in de organisatie en de resultaten van de klik:

- **Toegestaan:** de gebruiker mocht naar de URL navigeren.
- **Geblokkeerd:** De gebruiker is geblokkeerd voor het navigeren naar de URL.
- **Geblokkeerd en doorgeklikt:** De gebruiker heeft ervoor gekozen om door te gaan met navigeren naar de URL.
- **Doorgeklikt tijdens de scan:** De gebruiker heeft op de koppeling geklikt voordat de scan was voltooid.

Een klik geeft aan dat de gebruiker via de blokpagina naar de schadelijke website heeft geklikt (beheerders kunnen klikken uitschakelen in Safe Koppelingenbeleid).

Als u op **Filters** klikt, kunt u het rapport en de detailtabel wijzigen door een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:

- **Datum (UTC)**: **Begindatum** en **einddatum**
- **Detectie**:
  - **Toegestaan**
  - **Geblokkeerd**
  - **Geblokkeerd en doorgeklikt**
  - **Doorgeklikt tijdens de scan**
- **Domeinen:** de URL-domeinen die worden vermeld in de rapportresultaten.
- **Geadresseerden**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

De detailtabel onder de grafiek bevat de volgende bijna-realtime weergave van alle klikken die de afgelopen 7 dagen binnen de organisatie hebben plaatsgevonden:

- **Klik op tijd**
- **Gebruiker**
- **URL**
- **Actie**
- **App**

### <a name="view-data-by-url-click-by-application"></a>Gegevens weergeven op URL klik op toepassing

![URL-klik op toepassingsweergave in het rapport URL-bedreigingsbeveiliging](../../media/url-threat-protection-report-url-click-by-application-view.png)

In de weergave Gegevens **weergeven op URL op** toepassing wordt het aantal URL-klikken weergegeven door apps die ondersteuning bieden Safe Koppelingen:

- **E-mailclient**
- **PowerPoint**
- **Word**
- **Excel**
- **OneNote**
- **Visio**
- **Teams**
- **Anderen**

Als u op **Filters** klikt, kunt u het rapport en de detailtabel wijzigen door een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:

- **Datum (UTC)**: **Begindatum** en **einddatum**
- **Detectie:** Beschikbare apps in de grafiek.
- **Domeinen:** de URL-domeinen die worden vermeld in de rapportresultaten.
- **Geadresseerden**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

De detailtabel onder de grafiek bevat de volgende bijna-realtime weergave van alle klikken die de afgelopen 7 dagen binnen de organisatie hebben plaatsgevonden:

- **Klik op tijd**
- **Gebruiker**
- **URL**
- **Actie**
- **App**

## <a name="additional-reports-to-view"></a>Aanvullende rapporten die u wilt weergeven

Naast de rapporten die in dit artikel worden beschreven, zijn er verschillende andere rapporten beschikbaar, zoals beschreven in de volgende tabel:

<br>

****

|Rapport|Onderwerp|
|---|---|
|**Explorer** (Microsoft Defender voor Office 365 plan 2) of **realtime detecties** (Microsoft Defender voor Office 365 abonnement 1)|[Bedreigingsverkenner (en realtime detecties)](threat-explorer.md)|
|E-mailbeveiligingsrapporten waarvoor Defender niet nodig is voor Office 365|[E-mailbeveiligingsrapporten weergeven in de Microsoft 365 Defender portal](view-email-security-reports.md)|
|E-mailstroomrapporten in het Exchange-beheercentrum (EAC)|[E-mailstroomrapporten in het nieuwe Exchange beheercentrum](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|

PowerShell-rapportage-cmdlets:

<br>

****

|Rapport|Onderwerp|
|---|---|
|Belangrijkste afzenders en geadresseerden|[Get-MailTrafficTopReport](/powershell/module/exchange/get-mailtraffictopreport) <p> [Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|Top malware|[Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|E-mailverkeer|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <p> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|Veilige koppelingen|[Get-SafeLinksAggregateReport](/powershell/module/exchange/get-safelinksaggregatereport) <p> [Get-SafeLinksDetailReport](/powershell/module/exchange/get-safelinksdetailreport)|
|Gecompromitteerde gebruikers|[Get-CompromisedUserAggregateReport](/powershell/module/exchange/get-compromiseduseraggregatereport) <p> [Get-CompromisedUserDetailReport](/powershell/module/exchange/get-compromiseduserdetailreport)|
|E-mailstroomstatus|[Get-MailflowStatusReport](/powershell/module/exchange/get-mailflowstatusreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>Welke machtigingen zijn nodig om de Defender voor Office 365 weergeven?

Als u de rapporten wilt bekijken en gebruiken die in dit artikel worden beschreven, moet u lid zijn van een van de volgende rollengroepen in de Microsoft 365 Defender portal:

- **Organisatiebeheer**
- **Beveiligingsbeheerder**
- **Beveiligingslezer**
- **Globale lezer**

Zie [Machtigingen in de Microsoft 365 Defender-portal](permissions-microsoft-365-security-center.md) voor meer informatie.

**Opmerking:** Gebruikers toevoegen aan de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum geeft gebruikers de vereiste machtigingen in de _Microsoft 365 Defender-portal_ en machtigingen voor andere functies in Microsoft 365. Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="what-if-the-reports-arent-showing-data"></a>Wat gebeurt er als er geen gegevens worden weergegeven in de rapporten?

Als u geen gegevens ziet in uw Defender voor Office 365 rapporten, controleert u of uw beleid correct is ingesteld. Uw organisatie moet Safe [beleidsregels](set-up-safe-links-policies.md) voor koppelingen en Safe [bijlagen](set-up-safe-attachments-policies.md) hebben gedefinieerd, zodat Defender Office 365 beveiliging kan worden gebruikt. Zie ook [Anti-spam en anti-malwarebeveiliging.](anti-spam-and-anti-malware-protection.md)

## <a name="related-topics"></a>Gerelateerde onderwerpen

[Slimme rapporten en inzichten in de Microsoft 365 Defender portal](reports-and-insights-in-security-and-compliance.md)

[Rolmachtigingen (Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
