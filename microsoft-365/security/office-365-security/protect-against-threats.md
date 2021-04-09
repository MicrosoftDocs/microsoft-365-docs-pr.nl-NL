---
title: Beveiligen tegen bedreigingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen informatie krijgen over bedreigingsbeveiliging in Microsoft 365 en configureren hoe ze deze voor uw organisatie kunnen gebruiken.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2df88df9f1f0e2c14c0adcf0d5772189a1276e9d
ms.sourcegitcommit: a46532bb422ee51331f478ff50cc5444586bf6a9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2021
ms.locfileid: "51650228"
---
# <a name="protect-against-threats"></a>Beveiligen tegen bedreigingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Hier is een snelstarthandleiding die de configuratie van Defender voor Office 365 in stukken opbreekt. Als u nog niet zo bekend bent met functies voor bedreigingsbeveiliging in Office 365, weet u niet waar u moet beginnen of als u het beste leert door te *doen,* gebruikt u deze richtlijnen als controlelijst en uitgangspunt.

> [!IMPORTANT]
> **De eerste aanbevolen instellingen zijn opgenomen voor** elk type beleid. Er zijn echter veel opties beschikbaar en u kunt uw instellingen aanpassen aan de behoeften van uw specifieke organisatie. Sta ongeveer 30 minuten toe dat uw beleid of wijzigingen hun weg vinden in uw datacenter.

## <a name="requirements"></a>Vereisten

### <a name="subscriptions"></a>Abonnementen

Bedreigingsbeveiligingsfuncties zijn opgenomen in *alle* Microsoft- of Office 365-abonnementen. Sommige abonnementen hebben echter geavanceerde functies. De onderstaande tabel bevat de beveiligingsfuncties in dit artikel samen met de minimale abonnementsvereisten.

> [!TIP]
> Buiten de aanwijzingen voor het in- en uit- en in- en uit- zetten van *controle,* worden stappen uitgevoerd met anti-malware, anti-phishing en antispam, die zijn gemarkeerd als onderdeel van Office 365 Exchange Online Protection **(EOP).** Dit kan oneven lijken in een Defender voor Office 365-artikel, totdat u eraan herinnert (**Defender voor Office 365**) EOP bevat en verder bouwt.

****

|Beveiligingstype|Abonnementsvereiste|
|---|---|
|Auditregistratie (voor rapportagedoeleinden)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Beveiliging tegen malware|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) **(EOP)**|
|Bescherming tegen phishing|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Beveiliging tegen ongewenste e-mail|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Auto purge van nul uur (voor e-mail)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Bescherming tegen schadelijke URL's en bestanden in e-mail- en Office-documenten (veilige koppelingen en veilige bijlagen)|[Microsoft Defender voor Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Veilige bijlagen voor SharePoint-, OneDrive- en Microsoft Teams-werkbelastingen in- en uit-|[Defender voor Office 365](turn-on-mdo-for-spo-odb-and-teams.md)|
|Geavanceerde anti-phishingbeveiliging|[Defender voor Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Rollen en machtigingen

Als u Defender voor Office 365-beleid wilt configureren, moet u een passende rol krijgen toegewezen in het Beveiligings- [& Compliancecentrum.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) Bekijk de onderstaande tabel voor rollen die deze acties kunnen uitvoeren.

****

|Rol of rollengroep|Waar kunt u meer informatie?|
|---|---|
|globale beheerder|[Over Microsoft 365-beheersrollen](../../admin/add-users/about-admin-roles.md)|
|Beveiligingsbeheerder|[Machtigingen voor beheerdersrollen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online Organization Management|[Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) <p> en <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|

Zie Machtigingen in het Beveiligings- & [compliancecentrum voor meer informatie.](permissions-in-the-security-and-compliance-center.md)

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Voordat u begint, schakelt u Auditregistratie in voor rapportage en onderzoek

Begin de auditregistratie eerder. U moet controleren om on te zijn **voor** bepaalde stappen die volgen. Auditregistratie is beschikbaar in abonnementen met [Exchange Online.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) Als u gegevens wilt weergeven in bedreigingsbeveiligingsrapporten, zoals het beveiligingsdashboard, [](security-dashboard.md)e-mailbeveiligingsrapporten [en](view-email-security-reports.md) [Verkenner,](threat-explorer.md)moet auditregistratie zijn *aan.* Zie Zoeken in auditlogboek in- [of uitschakelen voor meer informatie.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>Deel 1 - Anti-malwarebeveiliging

[Anti-malwarebeveiliging](anti-malware-protection.md) is beschikbaar in abonnementen met [EOP.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. Kies in [& Beveiligingscentrum](https://protection.office.com)de optie **Bedreigingsbeheerbeleid** \>  \> **Anti-malware.**

2. Dubbelklik op het **standaardbeleid** en kies vervolgens **instellingen.**

3. Geef de volgende instellingen op:

    - Houd in **de sectie Reactie** op malwaredetectie de standaardinstelling **Nee.**

    - Kies in **de sectie Gemeenschappelijke bijlagetypenfilter** de optie **Aan**.

4. Klik op **Opslaan**.

Zie Anti-malwarebeleid configureren voor meer informatie over [anti-malwarebeleidsopties.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection"></a>Deel 2 - Bescherming tegen phishing

[Anti-phishingbeveiliging](anti-phishing-protection.md) is beschikbaar in abonnementen met [EOP.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Geavanceerde anti-phishingbeveiliging is beschikbaar in [Defender voor Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

In de volgende procedure wordt beschreven hoe u een anti-phishingbeleid configureert in Microsoft Defender voor Office 365. De stappen zijn vergelijkbaar voor het configureren van een anti-phishingbeleid in EOP.

1. Kies in [& Beveiligingscentrum](https://protection.office.com)de optie **Threat Management** \> **Policy** \> **ATP anti-phishing.**

2. Klik **op Standaardbeleid.**

3. Klik in **de sectie Imitatie** op **Bewerken** en geef de volgende instellingen op:

   - Schakel op **het tabblad Gebruikers toevoegen ter** beveiliging beveiliging *beveiliging* in. Voeg vervolgens gebruikers toe, zoals de leden van het bestuur van uw organisatie, uw CEO, CFO en andere senior leidinggevenden. (U kunt een afzonderlijk e-mailadres typen of klikken om een lijst weer te geven.)

   - Schakel op **het tabblad Domeinen toevoegen om te** beveiligen automatisch de domeinen in die ik **bezit.** Als u aangepaste domeinen hebt, voegt u deze nu toe.

   - Selecteer op **het** tabblad Acties de optie **Het bericht in** quarantaine plaatsen voor zowel de **imiteerde gebruiker** als de **nagebootsde domeinopties.** Schakel ook veiligheidstips voor imitatie in.

   - Zorg op het tabblad Postvakintelligentie ervoor dat postvakinformatie is ingeschakeld en schakel op postvakintelligentie gebaseerde imitatiebeveiliging in.  Kies in **de lijst Als e-mail wordt verzonden** door een nagebootsde gebruikerslijst de optie **Het bericht in quarantaine plaatsen.**

   - Geef op **het tabblad Vertrouwde afzenders en** domeinen toevoegen alle vertrouwde afzenders of domeinen op die u wilt toevoegen.

   - **Sla** op het **tabblad Uw instellingen controleren** op nadat u de instellingen hebt bekeken.

4. Klik in **de sectie Spoof** op **Bewerken** en geef de volgende instellingen op:

   - Zorg ervoor dat de beveiliging **tegen spoofing** is ingeschakeld op het tabblad Filterinstellingen voor spoofing.

   - Kies op **het** tabblad Acties de optie **Het bericht in quarantaine plaatsen.**

   - **Sla** op het **tabblad Uw instellingen controleren** op nadat u de wijzigingen hebt bekeken. (Als u geen wijzigingen hebt aangebracht, **annuleert** u .)

5. Sluit de pagina met standaardbeleidsinstellingen.

Zie Anti-phishingbeleid configureren in Microsoft Defender voor Office 365 voor meer informatie over uw [anti-phishingbeleidsopties.](configure-atp-anti-phishing-policies.md)

## <a name="part-3---anti-spam-protection"></a>Deel 3 - Bescherming tegen spam

[Antispambeveiliging](anti-spam-protection.md) is beschikbaar in abonnementen met [EOP.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. Kies in [& Beveiligingscentrum](https://protection.office.com)de optie **Bedreigingsbeheerbeleid** \>  \> **antispam.**

2. Schakel **aangepaste** instellingen in op het tabblad Aangepast.

3. Standaardbeleid **voor spamfilters** uitvV,klik op **Beleid bewerken** en geef de volgende instellingen op:

   - Stel in **de sectie Spam-** en bulkacties de drempelwaarde in op een waarde van 5 of 6.

   - Bekijk **(en/of** bewerk) in de sectie Lijsten toestaan uw toegestane afzenders en domeinen.

4. Klik op **Opslaan**.

Zie Antispambeleid configureren in EOP voor meer informatie over uw [antispambeleidsopties.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Deel 4 - Bescherming tegen schadelijke URL's en bestanden (Veilige koppelingen en veilige bijlagen in Defender voor Office 365)

Time-of-click-beveiliging tegen schadelijke URL's en bestanden is beschikbaar in abonnementen met [Microsoft Defender voor Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) Deze is ingesteld via beleidsregels voor [veilige bijlagen](safe-attachments.md) en [veilige](safe-links.md) koppelingen.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Beleid voor veilige bijlagen in Microsoft Defender voor Office 365

Als u veilige bijlagen [wilt instellen,](safe-attachments.md)maakt u ten minste één beleid voor veilige koppelingen.

1. Kies in [& Beveiligingscentrum](https://protection.office.com)de optie **Bedreigingsbeleid** \>  \> **ATP Safe Attachments** en klik vervolgens op **Maken.**

2. Configureer **de volgende** instellingen in de wizard Nieuw beleid voor veilige bijlagen die wordt weergegeven:

   - Typ in **het** vak Naam `Block malware` en klik vervolgens op **Volgende.**

   - Configureer **op de** pagina Instellingen de volgende instellingen:
     - Kies in **de sectie Veilige bijlagen onbekende malwarerespons** de optie **Blokkeren.**
     - Selecteer in **de sectie Bijlage** omleiden de optie **Omleiding inschakelen.** Geef het e-mailadres op voor de beveiligingsbeheerder of operator van uw organisatie, die gedetecteerde bestanden controleert.

     Klik op **Volgende**.

3. Klik op **de** pagina Toegepast op Een voorwaarde **toevoegen,** kies Toegepast als: Het domein van de geadresseerde **is,** klik op **Toevoegen,** selecteer uw domein of domeinen, klik op **Toevoegen,** klik op **Klaar** en klik vervolgens op **Volgende.**

4. Controleer de instellingen en klik vervolgens op **Voltooien.**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Beleid voor veilige koppelingen in Microsoft Defender voor Office 365

Als u Veilige koppelingen [wilt instellen,](safe-links.md)bekijkt en bewerkt u de algemene instellingen voor Veilige koppelingen en maakt u ten minste één beleid voor veilige koppelingen.

1. Kies in [& Beveiligingscentrum](https://protection.office.com)de  optie Beveiligingsbeheerbeleid \>  \> **ATP-veilige koppelingen** en klik op **Algemene** instellingen en configureer vervolgens de volgende instellingen:

   - Veilige **koppelingen gebruiken controleren in: Office 365-toepassingen** is ingeschakeld: Schakel ![ ](../../media/scc-toggle-on.png) in.
   - **Houd niet bij wanneer gebruikers op Veilige koppelingen** klikken: Schakel deze instelling uit om klikken van gebruikers bij te houden: ![ ](../../media/scc-toggle-off.png) Uitschakelen.
   - **Laat gebruikers niet door veilige koppelingen naar de oorspronkelijke URL** klikken: Controleer of deze instelling is ingeschakeld: Schakel ![ ](../../media/scc-toggle-on.png) in.

   Klik op **Opslaan** wanneer u gereed bent.

2. Klik op de hoofdpagina Veilige koppelingen op **Maken.**

3. Configureer **de volgende** instellingen in de wizard Beleid voor veilige koppelingen maken die wordt weergegeven:

   - Typ in **het** vak Naam een naam, zoals `Safe Links` , en klik vervolgens op **Volgende.**

   - Configureer **op de** pagina Instellingen de volgende instellingen:
     - **Selecteer de actie voor onbekende potentieel schadelijke URL's in berichten:** Kies **Aan.**
     - **Selecteer de actie voor onbekende of potentieel schadelijke URL's in Microsoft Teams:** Kies **Aan.**
     - **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie zijn verzonden**
     - **Wacht totdat URL-scannen is voltooid voordat u het bericht bezorgt**
     - **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie zijn verzonden**
     - **Gebruikers niet toestaan door te klikken naar de oorspronkelijke URL**

     Klik op **Volgende**.

4. Klik op **de** pagina Toegepast op Een voorwaarde **toevoegen,** kies Toegepast als: Het domein van de geadresseerde **is,** klik op **Toevoegen,** selecteer uw domein of domeinen, klik op **Toevoegen,** klik op **Klaar** en klik vervolgens op **Volgende.**

5. Controleer de instellingen en klik vervolgens op **Voltooien.**

Zie [Beleid voor veilige koppelingen instellen](set-up-safe-links-policies.md) voor meer informatie.

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Deel 5 : Veilige bijlagen controleren voor SharePoint, OneDrive en Microsoft Teams is ingeschakeld

Werkbelastingen zoals SharePoint, OneDrive en Teams zijn gemaakt voor samenwerking. Het gebruik van Defender voor Office 365 helpt bij het blokkeren en opsporen van bestanden die zijn geïdentificeerd als schadelijk in teamsites en documentbibliotheken. U kunt hier meer lezen over hoe dat [werkt.](mdo-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> Controleer voordat u deze procedure start of **auditlogregistratie al is ingeschakeld voor uw Microsoft 365-omgeving.** Dit wordt meestal gedaan door iemand aan wie de rol Auditlogboeken is toegewezen in Exchange Online. Zie Zoeken in [auditlogboek in- of uitschakelen voor meer informatie.](../../compliance/turn-audit-log-search-on-or-off.md)

1. Kies in [& Beveiligingscentrum](https://protection.office.com)de optie **Bedreigingsbeleid** \>  \> **ATP Safe Attachments** en klik vervolgens op **Algemene instellingen.**

2. Controleer of de schakelknop Defender voor **Office 365 voor SharePoint, OneDrive** en Microsoft Teams aan de rechterkant is in- of uitschakelen: Schakel in en klik vervolgens ![ op ](../../media/scc-toggle-on.png) **Opslaan.**

3. Controleer (en bewerk zo nodig) [](set-up-safe-attachments-policies.md) het beleid voor veilige bijlagen van uw organisatie en het [beleid voor veilige koppelingen.](set-up-safe-links-policies.md)

4. (Aanbevolen) Als globale beheerder of SharePoint Online-beheerder kunt u de cmdlet **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** uitvoeren met de parameter _DisallowInfectedFileDownload_ die is ingesteld op `$true` .

   - `$true` blokkeert alle acties (behalve Verwijderen) voor gedetecteerde bestanden. Personen kunnen gedetecteerde bestanden niet openen, verplaatsen, kopiëren of delen.
   - `$false` blokkeert alle acties, behalve Verwijderen en Downloaden. Personen kunnen ervoor kiezen om het risico te accepteren en een gedetecteerd bestand te downloaden.

   > [!TIP]
   > Zie Microsoft 365 beheren met PowerShell voor meer informatie over het gebruik van PowerShell met Microsoft [365.](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)

5. Sta maximaal 30 minuten toe dat uw wijzigingen worden verspreid naar alle Microsoft 365-datacenters.

### <a name="now-set-up-alerts-for-detected-files"></a>Nu waarschuwingen instellen voor gedetecteerde bestanden

Als u een melding wilt ontvangen wanneer een bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams is geïdentificeerd als schadelijk, kunt u een waarschuwing instellen.

1. Kies waarschuwingen beheren in &  [Beveiligings- en](https://protection.office.com) \> **compliancecentrum.**

2. Kies **Nieuw waarschuwingsbeleid.**

3. Geef een naam op voor de waarschuwing. U kunt bijvoorbeeld Schadelijke bestanden typen in bibliotheken.

4. Typ een beschrijving voor de waarschuwing. U kunt beheerders bijvoorbeeld een notififies typen wanneer schadelijke bestanden worden gedetecteerd in SharePoint Online, OneDrive of Microsoft Teams.

5. Stel in **de sectie Deze waarschuwing wanneer...** verzenden in:

   a. Kies in **de** lijst Activiteiten **de optie Gedetecteerde malware in bestand.**

   b. Laat het **veld Gebruikers** leeg.

6. Selecteer in de sectie Deze waarschuwing verzenden **naar...** een of meer globale beheerders, beveiligingsbeheerders of beveiligingslezers die een melding moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.

7. **Opslaan**.

Zie Activiteitswaarschuwingen maken in het beveiligings- & [compliancecentrum voor meer informatie over waarschuwingen.](../../compliance/create-activity-alerts.md)

> [!NOTE]
> Wanneer u klaar bent met configureren, gebruikt u deze koppelingen om werkbelastingsonderzoeken te starten:
>
>- [Statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
>- [Het beveiligings- & compliancecentrum gebruiken om in quarantaine geplaatste bestanden te beheren](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Wat moet u doen als er een schadelijk bestand wordt gevonden in SharePoint Online, OneDrive of Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Berichten en bestanden in quarantaine beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Deel 6 - Aanvullende instellingen om te configureren

Naast het configureren van beveiliging tegen malware, schadelijke URL's en bestanden, phishing en spam, raden we u aan om automatische 0-uurs purge te configureren.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Auto purge van nul uur voor e-mail in EOP

[Zap (Zero Hour Auto Purge)](zero-hour-auto-purge.md) is beschikbaar in abonnementen met [EOP.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Deze beveiliging is standaard ingeschakeld. Aan de volgende voorwaarden moet echter worden voldaan om de beveiliging van kracht te laten zijn:

- Spamacties zijn ingesteld op **Bericht verplaatsen naar map Ongewenste e-mail** in [antispambeleid.](anti-spam-protection.md)

- Gebruikers hebben hun standaardinstellingen voor ongewenste [e-mail behouden](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)en hebben de beveiliging van ongewenste e-mail niet uitgeschakeld.

Zie [Zero-hour Auto Purge - bescherming tegen spam en malware](zero-hour-auto-purge.md)voor meer informatie.

## <a name="post-setup-tasks-and-next-steps"></a>Taken na installatie en volgende stappen

Controleer na het configureren van de functies voor bedreigingsbeveiliging hoe deze functies werken. Controleer en wijzig uw beleid, zodat ze doen wat u nodig hebt. Let ook op nieuwe functies en service-updates die waarde kunnen toevoegen.

****

|Wat moet u doen?|Informatiebronnen|
|---|---|
|Bekijk hoe functies voor bedreigingsbeveiliging voor uw organisatie werken door rapporten te bekijken|[Beveiligingsdashboard](security-dashboard.md) <p> [E-mailbeveiligingsrapporten](view-email-security-reports.md) <p> [Rapporten voor Microsoft Defender voor Office 365](view-reports-for-mdo.md) <p> [Bedreigingsverkenner](threat-explorer.md)|
|Controleer uw beleid voor bedreigingsbeveiliging regelmatig en wijzig deze zo nodig|[Secure Score](../defender/microsoft-secure-score.md) <p> [Slimme rapporten en inzichten](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 threat investigation and response features](./office-365-ti.md)|
|Nieuwe functies en service-updates bekijken|[Standaard- en targeted releaseopties](../../admin/manage/release-options-in-office-365.md) <p> [Berichtencentrum](../../admin/manage/message-center.md) <p> [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Servicebeschrijvingen](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Meer informatie over aanbevolen standaard- en strikte beveiligingsconfiguraties voor EOP en Defender voor Office 365|[Aanbevolen instellingen voor EOP- en Microsoft Defender-beveiliging voor Office 365](recommended-settings-for-eop-and-office365.md)|
