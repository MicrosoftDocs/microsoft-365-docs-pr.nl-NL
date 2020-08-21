---
title: Beveiligen tegen bedreigingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie lezen over bedreigingsbeveiliging in Microsoft 365 en configureren hoe u deze voor uw organisatie gebruikt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8f1cecbb3141b4751778212025e5aad582707e12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826823"
---
# <a name="protect-against-threats"></a>Beveiligen tegen bedreigingen

Microsoft 365 omvat diverse functies voor beveiliging tegen bedreigingen. Aan de slag met een handleiding kunt u ervoor zorgen dat de functies voor beveiliging van bedreigingen voor uw organisatie zijn ingesteld. Als u nog niet bekend bent met de functies voor beveiliging van bedreigingen in Office 365, of als u niet zeker weet waar u moet beginnen, kunt u de volgende richtlijnen gebruiken als uitgangspunt.

> [!IMPORTANT]
> De **Aanbevolen instellingen worden voor elk type beleid opgenomen, maar er zijn veel opties beschikbaar en u kunt de instellingen aanpassen aan de behoeften van uw specifieke organisatie**. Sta ongeveer 30 minuten toe aan uw beleidsregels of wijzigingen die u kunt gebruiken in uw datacenter.

## <a name="requirements"></a>Vereisten

### <a name="subscriptions"></a>Abonnementen

De functies voor bedreigingsbeveiliging zijn opgenomen in alle Microsoft 365-abonnementen. Sommige abonnementen bevatten echter meer geavanceerde functies. De volgende tabel bevat een overzicht van de beveiligingsfuncties die in dit artikel zijn opgenomen, samen met de minimale abonnements vereisten.

****

|Type beveiliging|Vereisten voor het abonnement|
|---|---|
|Beveiliging tegen malware|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)|
|Beveiliging van schadelijke Url's en bestanden in e-mail en Office-documenten|[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)|
|Bescherming tegen phishing|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Geavanceerde anti malafide beveiliging|[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Beveiliging tegen ongewenste e-mail|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Automatisch wissen van 0 uur (voor e-mail)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Controlelogboekregistratie (dit wordt gebruikt voor rapportagedoeleinden)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>Rollen en machtigingen

U moet beschikken over de juiste rol voor het configureren van beleid in de [beveiligings & nalevings centrum](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). De volgende tabel bevat enkele voorbeelden:

****

|Rol of rollengroep|Waar vind ik meer informatie?|
|---|---|
|globale beheerder|[Over Microsoft 365-beheersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Beveiligingsbeheerder|[Machtigingen voor beheerdersrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Beheer van organisatie van Exchange Online|[Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>en<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Zie [machtigingen in het beveiligings &amp; centrum](permissions-in-the-security-and-compliance-center.md)voor meer informatie.

## <a name="part-1---anti-malware-protection"></a>Deel 1 – bescherming tegen malware

[Beveiliging tegen malware](anti-malware-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.

1. Kies in het [beveiligings & compliance](https://protection.office.com)de optie **Threat management**  >  **Policy**  >  **anti-malware**van beleid voor bedreigings beheer.

2. Dubbelklik op het **standaard** beleid en kies vervolgens **instellingen**.

3. Geef de volgende instellingen op:

    - In de sectie **Detectieantwoord van malware** moet u de standaardinstelling **Nee**opgeven.

    - Kies in de sectie **common Attachment types filter** de optie **on**.

4. Klik op **Opslaan**.

Zie [beleid voor malware van malware configureren](configure-anti-malware-policies.md)voor meer informatie over beleidsopties voor anti malware.

## <a name="part-2---protection-from-malicious-urls-and-files"></a>Deel 2-beveiliging van schadelijke Url's en bestanden

Beveiliging tegen tijd van schadelijke Url's en bestanden is beschikbaar in abonnementen die [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) bevatten en wordt ingesteld via [ATP veilige bijlagen](atp-safe-attachments.md) en profielen voor [veilige koppelingen](atp-safe-links.md) .

### <a name="atp-safe-attachments-policies"></a>Beleid voor veilige bijlagen met ATP

Voor het instellen van documenten met ATP voor de [vrije](atp-safe-attachments.md)tijd moet u minimaal één beleid voor veilige bijlagen met ATP definiëren.

1. Kies in het [beveiligings & compliance](https://protection.office.com)de optie voor het oplossen van **bedreigings beheer**  >  **beleid**voor  >  **veilige bijlagen**.

2. Selecteer de optie **ATP inschakelen voor SharePoint, OneDrive en Microsoft teams**.

3. Klik in de sectie **e-mailbijlagen beveiligen** op het plusteken ( **+** ).

4. Geef de volgende instellingen op:

   - Typ in het vak **naam** de tekst `Block malware` .

   - Kies in de sectie antwoord de optie **blok**.

   - Selecteer in de sectie **bijlage omleiden** de optie **omleiden inschakelen**en geef vervolgens het e-mailadres op van de beveiligingsbeheerder of operator van uw organisatie die gedetecteerde bestanden moet controleren.

   - Kies in de sectie **toegepast op** **het domein van de ontvanger**. Selecteer uw domein, kies **toevoegen**en klik vervolgens op **OK**.

5. Klik op **Opslaan**.

6. (**Aanbevolen extra stap**) Als globale beheerder of een SharePoint Online-beheerder voert u de cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uit waarbij de **DisallowInfectedFileDownload** -parameter is ingesteld op  *waar* voor uw Microsoft 365-omgeving. (Hiermee voorkomt u dat gebruikers bestanden openen, verplaatsen, kopiëren of delen die als schadelijk zijn gevonden.)

Zie voor meer informatie [office 365-beleid voor veilige bijlagen van office](set-up-atp-safe-attachments-policies.md) en [Schakel Office 365 ATP in voor SharePoint, OneDrive en Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>Beleid voor veilige koppelingen voor ATP

Voor het instellen van [veilige koppelingen voor ATP](atp-safe-links.md), controleert en bewerkt u uw standaardbeleid en voegt u een beleid toe voor specifieke gebruikers.

1. Kies in het [beveiligings & nalevings centrum](https://protection.office.com)de optie veilige koppelingen voor het beleid voor **bedreigings beheer**  >  **Policy**  >  **ATP Safe Links**.

2. Dubbelklik op het **standaard** beleid.

3. Selecteer in de sectie **veilige koppelingen gebruiken in** de optie **Microsoft 365-apps voor Enterprise, Office voor IOS en Android**, en klik vervolgens op **Opslaan**.

4. Klik in de sectie **beleidsregels die gelden voor specifieke geadresseerden** op het plusteken ( **+** ).

5. Geef de volgende instellingen op:

   - Typ een naam in het vak **naam** , zoals `Safe Links` .

   - Kies in de sectie **Selecteer de actie** **aan**.

   - Selecteer de volgende opties:

     - **Veilige bijlagen gebruiken om downloadbare inhoud te scannen**

     - **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden**

     - **Gebruikers niet laten klikken via veilige koppelingen naar de oorspronkelijke URL**

   - Kies in de sectie **toegepast op** **het domein van de ontvanger**. Selecteer uw domein, kies **toevoegen**en klik vervolgens op **OK**.

6. Klik op **Opslaan**.

Zie [Beleid voor veilige koppelingen in ATP instellen in Office 365](set-up-atp-safe-links-policies.md) voor meer informatie.

## <a name="part-3---anti-phishing-protection"></a>Deel 3: bescherming tegen phishing

[Anti-phishing]

[Bescherming tegen phishing](anti-phishing-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten. Geavanceerde beveiliging tegen phishing is beschikbaar in de [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

In de volgende procedure wordt beschreven hoe u een ATP anti-phishingfilter kunt configureren. De stappen zijn vergelijkbaar voor het configureren van een anti-phishingfilter-beleid (zonder ATP).

1. Kies in het [beveiligings & nalevings centrum](https://protection.office.com)de optie voor het instellen van het beleid voor het **beheer van bedreiging**  >  **Policy**  >  **ATP anti-phishing**.

2. Klik op **standaardbeleid**.

3. Klik in het gedeelte **imitatie** op **bewerken**en geef de volgende instellingen op:

   - Schakel op het tabblad **gebruikers toevoegen om** beveiliging in. Vervolgens voegt u gebruikers toe, zoals leden van de afdeling van uw organisatie, uw CEO, CFO en andere Senior leiders. (U kunt een apart e-mailadres typen of klikken om een lijst weer te geven.)

   - Schakel op het tabblad **domein toevoegen om te beschermen** **de optie automatisch de domeinnamen toevoegen waarvan ik de eigenaar**is in. Als u aangepaste domeinen hebt, kunt u deze ook toevoegen.

   - Selecteer op het tabblad **acties** **de optie quarantaine** voor de opties voor **geïmiteerde gebruiker** en **geïmiteerd domein** . Daarnaast schakelt u de veiligheidstips van de persoon in.

   - Zorg dat op het tabblad **Postvak Intelligence** de optie Postvak Intelligence is ingeschakeld. Schakel daarnaast ook de bescherming van imitatie via postvak in. Kies in het **e-mailbericht wordt verzonden door een geïmiteerde gebruikers** lijst **de optie Quarantine the Message**.

   - Geef op het tabblad **vertrouwde afzenders en domeinen toevoegen** de vertrouwde afzenders of domeinen op die u wilt toevoegen.

   - Wanneer u de instellingen hebt gecontroleerd, klikt u op het tabblad **uw instellingen controleren** op **Opslaan**.

4. Klik in de sectie **spoof** op **bewerken**en geef de volgende instellingen op:

   - Zorg dat op het tabblad **instellingen voor spoofing filter** de optie anti-spoofing beveiliging is ingeschakeld.

   - Kies op het tabblad **acties** **de optie Quarantine the Message**.

   - Wanneer u de instellingen hebt gecontroleerd, klikt u op het tabblad **uw instellingen controleren** op **Opslaan**. (Als u geen wijzigingen hebt aangebracht, klikt u op **Annuleren**.)

5. Sluit de standaardpagina met beleidsinstellingen.

Zie voor meer informatie over de opties voor het [instellen](configure-atp-anti-phishing-policies.md)van een anti-phishingfilter beleid.

## <a name="part-4---anti-spam-protection"></a>Deel 4-anti spam bescherming

[Bescherming tegen ongewenste e-mail](anti-spam-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.

1. Kies in het [beveiligings & compliance](https://protection.office.com)de optie **Threat management**  >  **Policy**  >  **anti-spam**beleid voor Threat Management.

2. Schakel op het tabblad **aangepast** de optie **aangepaste instellingen** in.

3. Vouw het **standaardbeleid voor spamfilters**uit, klik op **beleid bewerken**en geef de volgende instellingen op:

   - In de sectie **spam en Bulkacties** stelt u de drempelwaarde in op de waarde 5 of 6.

   - In het gedeelte **lijsten toestaan** controleert u de toegestane afzenders en domeinen en, indien nodig, bewerken.

4. Klik op **Opslaan**.

Zie [Antispambeleid in EOP](configure-your-spam-filter-policies.md)voor meer informatie over de opties voor anti-spam beleid.

## <a name="part-5---additional-settings-to-configure"></a>Deel 5-aanvullende instellingen voor het configureren van

U wordt aangeraden uw instellingen voor automatisch wissen van Zero-hours en logboekregistratie te configureren voor het automatisch opschonen van een uur van malware, schadelijke Url's en bestanden, phishing en spam.

### <a name="zero-hour-auto-purge-for-email"></a>Zero-Hour automatisch wissen voor e-mail

[Het gebruik van Zero-Hour auto leegmaak](zero-hour-auto-purge.md) (ZAP) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten. Deze bescherming is standaard ingeschakeld. u moet echter aan de volgende voorwaarden voldoen om beveiliging te activeren:

- Spam acties worden ingesteld op **bericht verplaatsen naar map Ongewenste e-mail** in [Antispambeleid](anti-spam-protection.md).

- Gebruikers hebben hun standaard [instellingen voor ongewenste](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)e-mail bewaard en hebben niet de bescherming tegen ongewenste e-mail uitgeschakeld.

Voor meer informatie raadpleegt u [Zero-Hour auto opgeschoond-bescherming tegen spam en malware](zero-hour-auto-purge.md).

### <a name="audit-logging-for-reporting-and-investigation"></a>Controlelogboekregistratie voor rapportage en onderzoek

Controlelogboekregistratie is beschikbaar voor abonnementen die [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)omvatten. Als u gegevens wilt weergeven in rapporten over bedreigingsbeveiliging, zoals het [beveiligings dashboard](security-dashboard.md), de [rapporten voor e-mail beveiliging](view-email-security-reports.md)en de [Verkenner](threat-explorer.md), moet u logboekregistratie inschakelen voor uw organisatie. Voor meer informatie raadpleegt u de [zoekfunctie voor auditlogboeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="post-setup-tasks"></a>Taken na de instelling

Nadat u uw beveiligingsfuncties hebt geconfigureerd, controleert u of de functies van deze functies werken, controleert u uw beleidsregels en wijzigt u deze naar wens, en bekijkt u de nieuwe functies en service-updates.

****

|Wat moet u doen?|Informatiebronnen|
|---|---|
|Kijk hoe de functies voor bedreigingsbeveiliging voor uw organisatie werken door rapporten weer te geven|[Beveiligings dashboard](security-dashboard.md)<br/>[E-mail beveiligingsrapporten](view-email-security-reports.md)<br/>[Rapporten voor Office 365 ATP](view-reports-for-atp.md)<br/>[Bedreigingsverkenner](threat-explorer.md)|
|Uw beveiligingsbeleid periodiek controleren en zo nodig herzien|[Secure Score](../mtp/microsoft-secure-score.md)<br/>[Slimme rapporten en inzichten](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 Threat onderzoek en antwoord functies](keep-users-safe-with-office-365-ti.md)|
|Bekijk de nieuwe functies en service-updates|[Standaard en gerichte release-opties](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Berichtencentrum](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Microsoft 365-wegwijzer](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Service beschrijvingen](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
