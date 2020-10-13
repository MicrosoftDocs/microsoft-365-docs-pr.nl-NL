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
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Beheerders kunnen informatie lezen over bedreigingsbeveiliging in Microsoft 365 en configureren hoe u deze voor uw organisatie gebruikt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 614d396fae2666baaa55f42323b68f93a08d2d92
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430929"
---
# <a name="protect-against-threats"></a>Beveiligen tegen bedreigingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Aan de slag-handleiding waarmee de configuratie van Advanced Threat Protection in segmenten wordt verbroken. Als u nog niet bekend bent met de functies voor beveiliging van bedreigingen in Office 365, weet u niet zeker waar u moet beginnen, of als u het beste kunt *doen*, gebruikt u deze instructies als een controlelijst en een beginpunt.

> [!IMPORTANT]
> De **Aanbevolen instellingen worden voor elk type beleid opgenomen, maar er zijn veel opties beschikbaar en u kunt de instellingen aanpassen aan de behoeften van uw specifieke organisatie**. Sta ongeveer 30 minuten toe aan uw beleidsregels of wijzigingen die u kunt gebruiken in uw datacenter.

## <a name="requirements"></a>Vereisten

### <a name="subscriptions"></a>Abonnementen

Functies voor beveiliging tegen bedreigingen zijn opgenomen in *alle* Microsoft-of Office 365-abonnementen. Sommige abonnementen hebben echter geavanceerde functies. In de onderstaande tabel vindt u een overzicht van de beveiligingsfuncties die in dit artikel zijn opgenomen, samen met de minimale abonnements vereisten.

> [!TIP]
> U ziet dat de stappen voor het inschakelen van de controle *stappen* niet werken met anti-malware, anti phishing en antispam, die zijn gemarkeerd als onderdeel van Office 365 Exchange Online Protection (**EOP**). Dit kan in een geavanceerd beveiligings artikel afwijkend lijken te zijn, totdat u de Advanced Threat Protection (**ATP**) weet, en bouwt op EOP.

****

|Type beveiliging|Vereisten voor het abonnement|
|---|---|
|Controlelogboekregistratie (voor rapportagedoeleinden)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Beveiliging tegen malware|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Bescherming tegen phishing|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Beveiliging tegen ongewenste e-mail|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Automatisch wissen van 0 uur (voor e-mail)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Beveiliging van schadelijke Url's en bestanden in e-mail en Office-documenten (veilige koppelingen en veilige bijlagen)|[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)|
|ATP voor SharePoint-, OneDrive-en Microsoft teams-workloads inschakelen|[GENOMEN](atp-for-spo-odb-and-teams.md)|
|Geavanceerde anti malafide beveiliging|[GENOMEN](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Rollen en machtigingen

Als u ATP-beleidsregels wilt configureren, moet u beschikken over de juiste rol in de [beveiligings & nalevings centrum](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Bekijk de onderstaande tabel voor rollen waarmee u deze acties kunt uitvoeren.

****

|Rol of rollengroep|Waar vind ik meer informatie?|
|---|---|
|globale beheerder|[Over Microsoft 365-beheersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Beveiligingsbeheerder|[Machtigingen voor beheerdersrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Beheer van organisatie van Exchange Online|[Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>en<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Zie [machtigingen in het beveiligings &amp; centrum](permissions-in-the-security-and-compliance-center.md)voor meer informatie.

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Voordat u begint, schakelt u audit logboekregistratie voor rapportage en onderzoek in

Start eerst uw auditlogboeken. U hebt controle **nodig voor de** volgende stappen. Controlelogboekregistratie is beschikbaar voor abonnementen die [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)omvatten. Als u gegevens wilt weergeven in rapporten over bedreigingsbeveiliging, zoals het [beveiligings dashboard](security-dashboard.md), de [rapporten voor e-mail beveiliging](view-email-security-reports.md)en [Verkenner](threat-explorer.md), moet logboekregistratie van gebeurtenissen zijn *ingeschakeld*. Voor meer informatie raadpleegt u de [zoekfunctie voor auditlogboeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="part-1---anti-malware-protection"></a>Deel 1 – bescherming tegen malware

[Beveiliging tegen malware](anti-malware-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.

1. Kies in het [beveiligings & compliance](https://protection.office.com)de optie **Threat management**  >  **Policy**  >  **anti-malware**van beleid voor bedreigings beheer.

2. Dubbelklik op het **standaard** beleid en kies vervolgens **instellingen**.

3. Geef de volgende instellingen op:

    - In de sectie **Detectieantwoord van malware** moet u de standaardinstelling **Nee**opgeven.

    - Kies in de sectie **common Attachment types filter** de optie **on**.

4. Klik op **Opslaan**.

Zie [beleid voor malware van malware configureren](configure-anti-malware-policies.md)voor meer informatie over beleidsopties voor anti malware.

## <a name="part-2---anti-phishing-protection"></a>Deel 2 – bescherming tegen phishing

[Anti-phishing]

[Bescherming tegen phishing](anti-phishing-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten. Geavanceerde beveiliging tegen phishing is beschikbaar in de [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

In de volgende procedure wordt beschreven hoe u een ATP anti-phishingfilter kunt configureren. De stappen zijn vergelijkbaar voor het configureren van een anti-phishingfilter-beleid (zonder ATP).

1. Kies in het [beveiligings & nalevings centrum](https://protection.office.com)de optie voor het instellen van het beleid voor het **beheer van bedreiging**  >  **Policy**  >  **ATP anti-phishing**.

2. Klik op **standaardbeleid**.

3. Klik in het gedeelte **imitatie** op **bewerken**en geef de volgende instellingen op:

   - Schakel op het tabblad **gebruikers toevoegen om** beveiliging in te schakelen *in* . Vervolgens voegt u gebruikers toe, zoals leden van de afdeling van uw organisatie, uw CEO, CFO en andere Senior leiders. (U kunt een apart e-mailadres typen of klikken om een lijst weer te geven.)

   - Schakel op het tabblad **domein toevoegen om te beschermen** **de optie automatisch de domeinnamen toevoegen waarvan ik de eigenaar**is in. Als u aangepaste domeinen hebt, kunt u deze nu toevoegen.

   - Selecteer op het tabblad **acties** **de optie quarantaine** voor de opties voor **geïmiteerde gebruiker** en **geïmiteerd domein** . Schakel ook de veiligheidstips van de persoon in.

   - Zorg dat op het tabblad **Postvak Intelligence** de optie Postvak Intelligence is ingeschakeld en schakel op basis van imitatie bescherming met postvak in. Kies in het **e-mailbericht wordt verzonden door een geïmiteerde gebruikers** lijst **de optie Quarantine the Message**.

   - Geef op het tabblad **vertrouwde afzenders en domeinen toevoegen** de vertrouwde afzenders of domeinen op die u wilt toevoegen.

   - **Sla** op het tabblad **uw instellingen controleren** nadat u de instellingen hebt gecontroleerd.

4. Klik in de sectie **spoof** op **bewerken**en geef de volgende instellingen op:

   - Zorg dat op het tabblad **instellingen voor spoofing filter** de optie anti-spoofing beveiliging is ingeschakeld.

   - Kies op het tabblad **acties** **de optie Quarantine the Message**.

   - **Sla** op het tabblad **uw instellingen controleren** na of u de wijzigingen hebt gecontroleerd. (Als u geen wijzigingen hebt aangebracht, **annuleert**.)

5. Sluit de standaardpagina met beleidsinstellingen.

Zie voor meer informatie over de opties voor het [instellen](configure-atp-anti-phishing-policies.md)van een anti-phishingfilter beleid.

## <a name="part-3---anti-spam-protection"></a>Deel 3-anti spam bescherming

[Bescherming tegen ongewenste e-mail](anti-spam-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.

1. Kies in het [beveiligings & compliance](https://protection.office.com)de optie **Threat management**  >  **Policy**  >  **anti-spam**beleid voor Threat Management.

2. Schakel op het tabblad **aangepast** de optie aangepaste instellingen in.

3. Vouw het **standaardbeleid voor spamfilters**uit, klik op **beleid bewerken**en geef de volgende instellingen op:

   - In de sectie **spam en Bulkacties** stelt u de drempelwaarde in op de waarde 5 of 6.

   - In het gedeelte **lijsten toestaan** controleert u de toegestane afzenders en domeinen (en/of bewerkt).

4. Klik op **Opslaan**.

Zie [Antispambeleid in EOP](configure-your-spam-filter-policies.md)voor meer informatie over de opties voor anti-spam beleid.

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-office-365-atp"></a>Deel 4-beveiliging van schadelijke Url's en bestanden (veilige koppelingen en veilige bijlagen in Office 365 ATP)

Beveiliging tegen tijd van schadelijke Url's en bestanden is beschikbaar in abonnementen die [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) bevatten. Het is geconfigureerd via [veilige bijlagen](atp-safe-attachments.md) en beleidsregels voor [veilige koppelingen](atp-safe-links.md) .

### <a name="safe-attachments-policies-in-office-365-atp"></a>Beleid voor veilige bijlagen in Office 365 ATP

Voor het instellen van [veilige bijlagen](atp-safe-attachments.md)maakt u minimaal één beleid voor veilige koppelingen.

1. Kies in het [beveiligings & compliance](https://protection.office.com)de optie voor het maken van **bedreigings beheer**  >  **beleidsregels**voor  >  **veilige bijlagen**en klik vervolgens op **maken**.

2. Configureer de volgende instellingen in de wizard **nieuwe beleidsregels voor veilige bijlagen** die wordt weergegeven:

   - Typ in het vak **naam** `Block malware` en klik op **volgende**.

   - Configureer de volgende instellingen op de pagina **instellingen** :
     - Kies in de sectie **veilige schadelijke software voor malware-antwoord** de optie **blokkeren**.
     - Selecteer in de sectie **bijlage omleiden** de optie **omleiden inschakelen**. Het e-mailadres opgeven voor de beheerder of operator van de beheerder van uw organisatie, die gedetecteerde bestanden controleert.

     Klik op **Volgende**.

3. Klik op de pagina **toegepast op** **een voorwaarde toevoegen**, kies **toegepast als: het domein van de ontvanger**, klik op **toevoegen**, selecteer uw domein of domeinen, klik op **toevoegen**, klik op **Voltooien**en klik op **volgende**.

4. Controleer de instellingen en klik vervolgens op **Voltooien**.

### <a name="safe-links-policies-in-office-365-atp"></a>Beleidsregels voor veilige koppelingen in Office 365 ATP

Voor het instellen van [veilige koppelingen](atp-safe-links.md), controleert u de algemene instellingen voor veilige koppelingen en maakt u minstens één beleid voor veilige koppelingen.

1. Kies in het [beveiligings & nalevings centrum](https://protection.office.com)de optie veilige koppelingen voor het beleid voor **bedreigings beheer**  >  **Policy**  >  **ATP Safe Links**en klik op **globale instellingen**en configureer de volgende instellingen:

   - Controleer de optie **veilige koppelingen gebruiken in: Office 365-toepassingen** is ingeschakeld: inschakelen ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .
   - **Niet bijhouden wanneer gebruikers op veilige koppelingen klikken**: Schakel deze instelling uit om de gebruikers klikken te volgen: ![ uit-/uitschakelen ](../../media/scc-toggle-off.png) .
   - **Gebruikers niet laten klikken via veilige koppelingen naar de oorspronkelijke URL**: Controleer of de optie is ingeschakeld: ingeschakeld ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   Klik op **Opslaan** wanneer u gereed bent.

2. Terug naar de hoofdpagina voor veilige koppelingen: Klik op **maken**.

3. Configureer de volgende instellingen in de wizard **beleid voor veilige koppelingen maken** die wordt weergegeven:

   - Typ een naam in het vak **naam** `Safe Links` en klik op **volgende**.

   - Configureer de volgende instellingen op de pagina **instellingen** :
     - **Selecteer de actie voor onbekende, mogelijk schadelijke url's in berichten**: Kies **aan**.
     - **Selecteer de actie voor onbekende of mogelijk schadelijke url's in Microsoft teams**: Kies **aan**.
     - **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden**
     - **Wachten tot URL-Scan is voltooid voordat het bericht wordt bezorgd**
     - **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden**
     - **Gebruikers kunnen niet naar de oorspronkelijke URL klikken**

     Klik op **Volgende**.

4. Klik op de pagina **toegepast op** **een voorwaarde toevoegen**, kies **toegepast als: het domein van de ontvanger**, klik op **toevoegen**, selecteer uw domein of domeinen, klik op **toevoegen**, klik op **Voltooien**en klik op **volgende**.

5. Controleer de instellingen en klik vervolgens op **Voltooien**.

Zie [Beleid voor veilige koppelingen instellen](set-up-atp-safe-links-policies.md) voor meer informatie.

## <a name="part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Deel 5-de ATP voor SharePoint, OneDrive en Microsoft teams ingeschakeld laten

Werkbelastingen, zoals SharePoint, OneDrive en teams, zijn ontwikkeld voor samenwerking. Met ATP kunt u bestanden die zijn geïdentificeerd als schadelijk op team sites en documentbibliotheken, blokkeren en detecteren. Lees [hier](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)meer over het werken.

> [!IMPORTANT]
> **Voordat u met deze procedure begint, controleert u of logboekregistratie al is ingeschakeld voor uw Microsoft 365-omgeving**. Dit gebeurt meestal door iemand die de rol audit logboeken heeft toegewezen in Exchange Online. Zie [auditlogboek zoeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.

1. Kies in het [beveiligings & compliance](https://protection.office.com)de optie voor het oplossen van **bedreigings beheer**  >  **beleidsregels**voor  >  **veilige bijlagen**en klik vervolgens op **algemene instellingen**.

2. Controleer of de wisselknop **ATP voor SharePoint, OneDrive en Microsoft teams in-of uitschakelen** aan de rechterkant: inschakelen ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) en klik vervolgens op **Opslaan**.

3. Bekijk (en, indien nodig, bewerken) het beleid voor [veilige bijlagen](set-up-atp-safe-attachments-policies.md) van uw organisatie en het [beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md).

4. Beter Als globale beheerder of een SharePoint Online-beheerder voert u de cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uit waarbij de _DisallowInfectedFileDownload_ -parameter is ingesteld op `$true` .

   - `$true` alle acties (met uitzondering van verwijdering) voor gedetecteerde bestanden blokkeren. Personen kunnen geen gevonden bestanden openen, verplaatsen, kopiëren of delen.
   - `$false` alle acties blokkeren behalve verwijderen en downloaden. Gebruikers kunnen ervoor kiezen het risico te accepteren en een gevonden bestand te downloaden.

   > [!TIP]
   > Zie [Microsoft 365 beheren met PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)voor meer informatie over het gebruik van PowerShell met microsoft 365.

5. Maximaal 30 minuten wachten tot de wijzigingen zijn doorgevoerd naar alle Microsoft 365-datacenters.

### <a name="now-set-up-alerts-for-detected-files"></a>Nu waarschuwingen voor gedetecteerde bestanden instellen

Als u een melding wilt ontvangen wanneer een bestand in SharePoint Online, OneDrive voor bedrijven of Microsoft teams is herkend als schadelijk, kunt u een melding instellen.

1. Kies in het [beveiligings & nalevings centrum](https://protection.office.com) **waarschuwingen** \> **beheren**.

2. Kies **Nieuw waarschuwings beleid**.

3. Geef een naam op voor de waarschuwing. U kunt bijvoorbeeld schadelijke bestanden in bibliotheken typen.

4. Typ een beschrijving voor de waarschuwing. U kunt bijvoorbeeld een melding van de beheerder doen wanneer er kwaadaardige bestanden zijn gevonden in SharePoint Online, OneDrive of Microsoft teams.

5. Zet in de sectie **Deze waarschuwing verzenden wanneer...** de volgende opties:

   a. Kies in de lijst **activiteiten** de optie **malware gevonden in bestand**.

   b. Laat het veld **gebruikers** leeg.

6. Selecteer in de sectie **Deze waarschuwing verzenden naar...** een of meer globale beheerders, beveiligingsbeheerders of beveiligings lezers die een bericht moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.

7. **Save**.

Zie voor meer informatie over waarschuwingen [activiteiten meldingen maken in het beveiligings & nalevings centrum](../../compliance/create-activity-alerts.md).

> [!NOTE]
> Wanneer u klaar bent met de configuratie, kunt u de volgende koppelingen gebruiken om werkbelasting te onderzoeken:
>
>- [Statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
>- [De beveiligings & gebruiken om in quarantaine geplaatste bestanden te beheren](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Wat u moet doen als er een schadelijk bestand wordt gevonden in SharePoint Online, OneDrive of Microsoft teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [In quarantaine geplaatste berichten en bestanden als beheerder beheren in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Deel 6-aanvullende instellingen om te configureren

Als u de beveiliging van malware, schadelijke Url's en bestanden, phishing en spam verveiligt, wordt u aangeraden om automatisch wissen van Zero uur te configureren.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Zero-Hour automatisch wissen voor e-mail in EOP

[Het gebruik van Zero-Hour auto leegmaak](zero-hour-auto-purge.md) (ZAP) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten. Deze bescherming is standaard ingeschakeld. u moet echter aan de volgende voorwaarden voldoen om beveiliging te activeren:

- Spam acties worden ingesteld op **bericht verplaatsen naar map Ongewenste e-mail** in [Antispambeleid](anti-spam-protection.md).

- Gebruikers hebben hun standaard [instellingen voor ongewenste](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)e-mail bewaard en hebben de bescherming tegen ongewenste e-mail uitgeschakeld.

Voor meer informatie raadpleegt u [Zero-Hour auto opgeschoond-bescherming tegen spam en malware](zero-hour-auto-purge.md).

## <a name="post-setup-tasks-and-next-steps"></a>Taken na de installatie en volgende stappen

Nadat u de functies voor risico beveiliging hebt geconfigureerd, controleert u of u de werking van deze functies controleert. Bekijk en wijzig uw beleidsregels zodat u ze kunt uitvoeren. Kijk ook naar nieuwe functies en service-updates die een waarde kunnen toevoegen.

****

|Wat moet u doen?|Informatiebronnen|
|---|---|
|Kijk hoe de functies voor bedreigingsbeveiliging voor uw organisatie werken door rapporten weer te geven|[Beveiligings dashboard](security-dashboard.md)<br/>[E-mail beveiligingsrapporten](view-email-security-reports.md)<br/>[Rapporten voor Office 365 ATP](view-reports-for-atp.md)<br/>[Bedreigingsverkenner](threat-explorer.md)|
|Uw beveiligingsbeleid periodiek controleren en zo nodig herzien|[Secure Score](../mtp/microsoft-secure-score.md)<br/>[Slimme rapporten en inzichten](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 Threat onderzoek en antwoord functies](keep-users-safe-with-office-365-ti.md)|
|Bekijk de nieuwe functies en service-updates|[Standaard en gerichte release-opties](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Berichtencentrum](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Service beschrijvingen](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Meer informatie over aanbevolen standaard-en strikte beveiligingsconfiguraties voor EOP en ATP|[Aanbevolen instellingen voor EOP en Office 365 ATP-beveiliging](recommended-settings-for-eop-and-office365-atp.md)|
