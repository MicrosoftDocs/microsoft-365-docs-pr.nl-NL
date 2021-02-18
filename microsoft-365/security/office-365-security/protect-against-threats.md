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
description: Beheerders kunnen meer informatie krijgen over bedreigingsbeveiliging in Microsoft 365 en hoe ze dit kunnen gebruiken voor uw organisatie.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c9ca420609628476faba6262fe7ed412b8fa5746
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288799"
---
# <a name="protect-against-threats"></a>Beveiligen tegen bedreigingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Hier is een beknopte handleiding die de configuratie van Defender voor Office 365 in segmenten opbreekt. Als u nog niet bekend bent met functies voor risicobeveiliging in Office 365, niet zeker weet waar u moet beginnen of als u het beste *leert,* gebruikt u deze richtlijnen als controlelijst en uitgangspunt.

> [!IMPORTANT]
> De eerste aanbevolen instellingen zijn opgenomen voor elk soort beleid. Er zijn echter veel opties beschikbaar en u kunt uw instellingen aanpassen aan de specifieke behoeften **van uw organisatie.** Het duurt ongeveer 30 minuten voordat uw beleidsregels of wijzigingen zijn doorgevoerd in uw datacenter.

## <a name="requirements"></a>Vereisten

### <a name="subscriptions"></a>Abonnementen

Bedreigingsbeveiligingsfuncties zijn opgenomen in *alle* Microsoft- of Office 365-abonnementen; Sommige abonnementen hebben echter geavanceerde functies. De onderstaande tabel bevat de beveiligingsfuncties in dit artikel samen met de minimale abonnementsvereisten.

> [!TIP]
> U ziet dat u naast de aanwijzingen  voor het in- en uitvoeren van controles ook antimalware, anti-phishing en antispamstappen kunt starten, die zijn gemarkeerd als onderdeel van Office 365 Exchange Online Protection **(EOP).** Dit kan oneven lijken in een artikel van Defender voor Office 365, totdat u weet dat (Defender voor **Office 365)** EOP bevat en verder bouwt.

****

|Beveiligingstype|Abonnementsvereiste|
|---|---|
|Controlelogregistratie (voor rapportagedoeleinden)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Beveiliging tegen malware|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) **(EOP)**|
|Bescherming tegen phishing|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Beveiliging tegen ongewenste e-mail|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Automatisch nul-uurs purge (voor e-mail)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Bescherming tegen schadelijke URL's en bestanden in e-mail- en Office-documenten (veilige koppelingen en veilige bijlagen)|[Microsoft Defender voor Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Veilige bijlagen voor SharePoint-, OneDrive- en Microsoft Teams-werkbelastingen in schakel|[Defender voor Office 365 ](atp-for-spo-odb-and-teams.md)|
|Geavanceerde beveiliging tegen phishing|[Defender voor Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Rollen en machtigingen

Als u Defender voor Office 365-beleid wilt configureren, moet u een relevante rol toegewezen krijgen in het & [compliancecentrum.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) In de onderstaande tabel ziet u welke rollen deze acties kunnen uitvoeren.

****

|Rol of rollengroep|Waar meer informatie|
|---|---|
|globale beheerder|[Over Microsoft 365-beheersrollen](../../admin/add-users/about-admin-roles.md)|
|Beveiligingsbeheerder|[Machtigingen voor beheerdersrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online-organisatiebeheer|[Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> en <p> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Zie Machtigingen in het beveiligings- en & [voor meer informatie.](permissions-in-the-security-and-compliance-center.md)

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Voordat u begint, moet u auditlogregistratie voor rapportage en onderzoek inschakelen

Start de auditlogregistratie vroeg. Voor bepaalde stappen die volgen, moet **u** controleren of deze aan staat. Controlelogregistratie is beschikbaar in abonnementen die [Exchange Online bevatten.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) Als u gegevens in risicobeveiligingsrapporten [](security-dashboard.md)wilt weergeven, zoals het beveiligingsdashboard, [e-mailbeveiligingsrapporten](view-email-security-reports.md)en [Explorer,](threat-explorer.md)moet auditlogregistratie zijn aan *staan.* Zie Zoeken in [auditlogboek in- of uitschakelen voor meer informatie.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>Deel 1- Bescherming tegen malware

[Bescherming tegen malware](anti-malware-protection.md) is beschikbaar in abonnementen die [EOP bevatten.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. Kies in [het & Compliancecentrum voor](https://protection.office.com)beveiligingsbeleid de optie **Bedreigingsbeheerbeleid** \>  \> **anti-malware.**

2. Dubbelklik op het **standaardbeleid** en kies vervolgens **instellingen.**

3. Geef de volgende instellingen op:

    - Laat in **de sectie Reactie** van malwaredetectie de standaardinstelling Nee **staan.**

    - Kies in **de sectie Filter voor veelvoorkomende** bijlagetypen de optie **Op.**

4. Klik op **Opslaan**.

Zie [Antimalwarebeleid](configure-anti-malware-policies.md)configureren voor meer informatie over beleidsopties voor malware.

## <a name="part-2---anti-phishing-protection"></a>Deel 2 - Beveiliging tegen phishing

[Beveiliging tegen phishing](anti-phishing-protection.md) is beschikbaar in abonnementen met [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Geavanceerde beveiliging tegen phishing is beschikbaar in [Defender voor Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

In de volgende procedure wordt beschreven hoe u een anti-phishingbeleid configureert in Microsoft Defender voor Office 365. De stappen zijn vergelijkbaar met het configureren van een anti-phishingbeleid in EOP.

1. Kies in [het & Compliancecentrum voor](https://protection.office.com)beveiligingsbeleid de optie  \>  \> **RISICOBEHEERBELEID ATP anti-phishing.**

2. Klik **op Standaardbeleid.**

3. Klik in **de sectie Imitatie** op **Bewerken** en geef de volgende instellingen op:

   - Schakel op **het tabblad Gebruikers toevoegen ter beveiliging** de beveiliging *in.* Voeg vervolgens gebruikers toe, zoals de leden van de raad van bestuur van uw organisatie, uw CEO, CFO en andere senior leidinggevenden. (U kunt een afzonderlijk e-mailadres typen of klikken om een lijst weer te geven.)

   - Schakel op **het tabblad Domeinen toevoegen om** de beveiliging te beveiligen automatisch de domeinen in die ik **bezit.** Als u aangepaste domeinen hebt, kunt u deze nu toevoegen.

   - Selecteer op **het tabblad** Acties de optie **Quarantaine voor** het bericht voor zowel de **gemiteerde gebruiker** als voor opties voor **gemitmiteerde** domeinen. Schakel ook veiligheidstips voor imitatie in.

   - Zorg ervoor **dat postvakinformatie** is ingeschakeld op het tabblad Postvakinformatie en schakel imitatiebeveiliging op basis van postvakinformatie in. Kies In de **lijst Als e-mail wordt verzonden door een gemitmiteerde gebruikerslijst,** kiest u **Het bericht in quarantaine plaatsen.**

   - Geef op **het tabblad Vertrouwde afzenders** en domeinen toevoegen eventuele vertrouwde afzenders of domeinen op die u wilt toevoegen.

   - **Sla** op het **tabblad Uw instellingen controleren** op nadat u de instellingen hebt bekeken.

4. Klik in **de sectie Adresvervalsing** op **Bewerken** en geef de volgende instellingen op:

   - Zorg ervoor **dat de** beveiliging tegen adresvervalsing is ingeschakeld op het tabblad met filterinstellingen voor adresvervalsing.

   - Kies het **bericht** in quarantaine op **het tabblad Acties.**

   - **Sla** op het **tabblad Uw instellingen controleren** op nadat u uw wijzigingen hebt bekeken. (Als u geen wijzigingen hebt aangebracht, **annuleert u**.)

5. Sluit de pagina met standaardbeleidsinstellingen.

Zie Anti-phishingbeleid configureren in [Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)voor meer informatie over de opties voor anti-phishingbeleid.

## <a name="part-3---anti-spam-protection"></a>Deel 3 - Bescherming tegen ongewenste e-mail

[Beveiliging tegen ongewenste e-mail](anti-spam-protection.md) is beschikbaar in abonnementen die [EOP bevatten.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. Kies in [het & Compliancecentrum voor](https://protection.office.com)beveiligingsbeleid **de** optie \> **Risicobeheerbeleid** \> **antispam.**

2. Schakel aangepaste **instellingen** in op het tabblad Aangepast.

3. Vouw **standaardbeleid voor spamfilters uit,** klik op Beleid **bewerken** en geef de volgende instellingen op:

   - Stel in **de sectie Spam- en bulkacties** de drempelwaarde in op 5 of 6.

   - Bekijk **(en/of** bewerk) uw toegestane afzenders en domeinen in de sectie Lijsten toestaan.

4. Klik op **Opslaan**.

Zie Antispambeleid configureren in EOP voor meer informatie over de opties voor [antispambeleid.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Deel 4: bescherming tegen schadelijke URL's en bestanden (veilige koppelingen en veilige bijlagen in Defender voor Office 365)

Time-of-click-beveiliging tegen schadelijke URL's en bestanden is beschikbaar in abonnementen met [Microsoft Defender voor Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) Dit wordt ingesteld via een beleid voor [veilige bijlagen](atp-safe-attachments.md) en [veilige](atp-safe-links.md) koppelingen.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Beleid voor veilige bijlagen in Microsoft Defender voor Office 365

Als u veilige bijlagen [wilt instellen,](atp-safe-attachments.md)moet u ten minste één beleid voor veilige koppelingen maken.

1. Kies in [het & Compliancecentrum](https://protection.office.com)  voor beveiligingsbeheer de optie Veilige bijlagen met \>  \> **RISICObeheer ATP** en klik op **Maken.**

2. Configureer **de volgende** instellingen in de wizard Nieuw beleid voor veilige bijlagen die wordt weergegeven:

   - Typ in **het** vak Naam `Block malware` en klik op **Volgende.**

   - Configureer **de volgende** instellingen op de pagina Instellingen:
     - Kies Blokkeren **in de sectie Onbekende malwarereactie veilige** bijlagen. 
     - Selecteer in **de sectie Bijlage omleiden** de optie **Omleiding inschakelen.** Geef het e-mailadres op van de beveiligingsbeheerder of operator van uw organisatie, die gedetecteerde bestanden gaat controleren.

     Klik op **Volgende**.

3. Klik op **de** pagina Toegepast op een voorwaarde toevoegen, kies Toegepast als: Het domein van de geadresseerde **is,** klik op **Toevoegen,** selecteer uw domein of domeinen, klik op **Toevoegen,** klik op Klaar en klik vervolgens op **Volgende.**

4. Controleer de instellingen en klik op **Voltooien.**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Beleid voor veilige koppelingen in Microsoft Defender voor Office 365

Als u veilige koppelingen [wilt instellen,](atp-safe-links.md)controleert en bewerkt u de globale instellingen voor veilige koppelingen en maakt u ten minste één beleid voor veilige koppelingen.

1. Kies in [het & Compliancecentrum](https://protection.office.com)voor beveiligingsbeleid de optie Veilige koppelingen van  ATP voor bedreigingsbeheer, klik op Algemene instellingen en configureer \>  \> de volgende instellingen: 

   - Controleer **gebruik van veilige koppelingen in: Office 365-toepassingen** is ingeschakeld: ![ in-/uitschakelen. ](../../media/scc-toggle-on.png)
   - **Houd niet bij wanneer gebruikers op Veilige koppelingen** klikken: schakel deze instelling uit om klikken van gebruikers bij te houden: Schakel deze instelling ![ ](../../media/scc-toggle-off.png) uit.
   - **Laat gebruikers niet door veilige koppelingen naar de oorspronkelijke URL** klikken: controleer of deze instelling is ingeschakeld: ![ In-/uitschakelen. ](../../media/scc-toggle-on.png)

   Klik op **Opslaan** wanneer u gereed bent.

2. Klik weer op de hoofdpagina met veilige koppelingen op **Maken.**

3. Configureer **de volgende** instellingen in de wizard Beleid voor veilige koppelingen maken die wordt weergegeven:

   - Typ in **het** vak Naam een naam, zoals `Safe Links` , en klik vervolgens op **Volgende.**

   - Configureer **de volgende** instellingen op de pagina Instellingen:
     - **Selecteer de actie voor onbekende, mogelijk schadelijke URL's in berichten:** Kies **aan.**
     - **Selecteer de actie voor onbekende of mogelijk schadelijke URL's in Microsoft Teams:** Kies **op.**
     - **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden**
     - **Wacht totdat het scannen van de URL is voltooid voordat het bericht wordt weergegeven**
     - **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden**
     - **Gebruikers niet toestaan door te klikken naar de oorspronkelijke URL**

     Klik op **Volgende**.

4. Klik op **de** pagina Toegepast op een voorwaarde toevoegen, kies Toegepast als: Het domein van de geadresseerde **is,** klik op **Toevoegen,** selecteer uw domein of domeinen, klik op **Toevoegen,** klik op Klaar en klik vervolgens op **Volgende.**

5. Controleer de instellingen en klik op **Voltooien.**

Zie [Beleid voor veilige koppelingen instellen](set-up-atp-safe-links-policies.md) voor meer informatie.

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Deel 5: Veilige bijlagen controleren voor SharePoint, OneDrive en Microsoft Teams is ingeschakeld

Werkbelastingen zoals SharePoint, OneDrive en Teams zijn ontworpen voor samenwerking. Het gebruik van Defender voor Office 365 helpt bij het blokkeren en detecteren van bestanden die worden geïdentificeerd als schadelijk in teamsites en documentbibliotheken. Hier vindt u meer informatie over hoe dat [werkt.](atp-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> Controleer voordat u met deze procedure begint of **auditlogregistratie al is ingeschakeld voor uw Microsoft 365-omgeving.** Dit wordt meestal gedaan door iemand aan wie de rol Auditlogboeken is toegewezen in Exchange Online. Zie Zoeken in [auditlogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.

1. Kies in [het & compliancecentrum](https://protection.office.com)  voor risicobeheerbeleid VEILIGE bijlagen met ATP en klik \>  \> op **Globale instellingen.**

2. Controleer of de schakelknop Defender voor **Office 365 voor SharePoint, OneDrive** en Microsoft Teams rechts is in- of uitschakelen en klik op ![ ](../../media/scc-toggle-on.png) **Opslaan.**

3. Controleer (en bewerk, waar nodig), [](set-up-atp-safe-attachments-policies.md) het beleid voor veilige bijlagen en het beleid voor veilige koppelingen [van uw organisatie.](set-up-atp-safe-links-policies.md)

4. (Aanbevolen) Als globale beheerder of SharePoint Online-beheerder kunt u de cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uitvoeren met de parameter _DisallowInfectedFileDownload_ ingesteld op `$true` .

   - `$true` alle acties (met uitzondering van Verwijderen) voor gedetecteerde bestanden worden blokkeert. Mensen kunnen gedetecteerde bestanden niet openen, verplaatsen, kopiëren of delen.
   - `$false` hiermee blokkeert u alle acties, met uitzondering van Verwijderen en Downloaden. Mensen kunnen ervoor kiezen om het risico te accepteren en een gedetecteerd bestand te downloaden.

   > [!TIP]
   > Zie Microsoft 365 beheren met PowerShell voor meer informatie over het gebruik van [PowerShell met Microsoft 365.](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)

5. Het kan 30 minuten duren voordat de wijzigingen zijn doorgevoerd naar alle Microsoft 365-datacenters.

### <a name="now-set-up-alerts-for-detected-files"></a>Nu waarschuwingen instellen voor gedetecteerde bestanden

Als u een melding wilt ontvangen wanneer een bestand in SharePoint Online, OneDrive voor Bedrijven of Microsoft Teams als schadelijk is geïdentificeerd, kunt u een waarschuwing instellen.

1. Kies [waarschuwingen beheren in & compliancecentrum](https://protection.office.com)  \> **voor waarschuwingen.**

2. Kies **Nieuw waarschuwingsbeleid.**

3. Geef een naam op voor de waarschuwing. U kunt bijvoorbeeld schadelijke bestanden typen in bibliotheken.

4. Typ een beschrijving voor de waarschuwing. U kunt bijvoorbeeld Een e-mailbeheerder typen als er schadelijke bestanden worden aangetroffen in SharePoint Online, OneDrive of Microsoft Teams.

5. Stel in **de sectie Deze waarschuwing verzenden wanneer...** het volgende in:

   a. Kies In de **lijst** Activiteiten de **optie Gedetecteerde malware in bestand.**

   b. Laat het **veld Gebruikers** leeg.

6. Selecteer in de sectie Deze waarschuwing verzenden **naar...** een of meer globale beheerders, beveiligingsbeheerders of beveiligingslezers die een melding moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.

7. **Opslaan.**

Zie Activiteitswaarschuwingen maken in het beveiligings- & compliancecentrum voor meer informatie [over waarschuwingen.](../../compliance/create-activity-alerts.md)

> [!NOTE]
> Wanneer u klaar bent met configureren, gebruikt u deze koppelingen om werkbelastingsonderzoek te starten:
>
>- [Statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
>- [Het beveiligings- & voor het beheren van bestanden in quarantaine](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Wat moet u doen als er een schadelijk bestand wordt gevonden in SharePoint Online, OneDrive of Microsoft Teams?](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Berichten en bestanden in quarantaine beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Deel 6: Aanvullende instellingen om te configureren

Naast het configureren van de beveiliging tegen malware, schadelijke URL's en bestanden, phishing en spam, raden we u aan om automatisch verwijderen in een uur tijd te configureren.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Zero-hour auto purge for email in EOP

[Zero-hour Auto Purge](zero-hour-auto-purge.md) (ZAP) is beschikbaar in abonnementen die [EOP bevatten.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Deze beveiliging is standaard ingeschakeld. Als de beveiliging van kracht is, moet echter aan de volgende voorwaarden worden voldaan:

- Spamacties zijn ingesteld op **Bericht verplaatsen naar map Ongewenste e-mail** in [antispambeleid.](anti-spam-protection.md)

- Gebruikers hebben hun standaardinstellingen [voor ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)behouden en hebben de bescherming tegen ongewenste e-mail niet uitgeschakeld.

Zie [Zero-hour Auto Purge - beveiliging tegen spam en malware voor meer informatie.](zero-hour-auto-purge.md)

## <a name="post-setup-tasks-and-next-steps"></a>Post-setup tasks and next steps

Controleer na het configureren van de functies voor bedreigingsbeveiliging hoe deze functies werken. Controleer en wijzig uw beleid, zodat ze doen wat u nodig hebt. Let ook op nieuwe functies en service-updates die waarde kunnen toevoegen.

****

|Wat moet u doen?|Informatiebronnen|
|---|---|
|Bekijk hoe functies voor bedreigingsbeveiliging voor uw organisatie werken door rapporten weer te bieden|[Beveiligingsdashboard](security-dashboard.md) <p> [Beveiligingsrapporten via e-mail verzenden](view-email-security-reports.md) <p> [Rapporten voor Microsoft Defender voor Office 365](view-reports-for-atp.md) <p> [Bedreigingsverkenner](threat-explorer.md)|
|Uw beleid voor risicobeveiliging zo nodig regelmatig controleren en herzien|[Secure Score](../mtp/microsoft-secure-score.md) <p> [Slimme rapporten en inzichten](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365-functies voor bedreigingsonderzoek en -antwoorden](keep-users-safe-with-office-365-ti.md)|
|Let op nieuwe functies en service-updates|[Standard Release- en Targeted Release-opties](../../admin/manage/release-options-in-office-365.md) <p> [Berichtencentrum](../../admin/manage/message-center.md) <p> [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Servicebeschrijvingen](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Meer informatie over aanbevolen standaard- en strikte beveiligingsconfiguraties voor EOP en Defender voor Office 365|[Aanbevolen instellingen voor EOP- en Microsoft Defender voor Office 365-beveiliging](recommended-settings-for-eop-and-office365-atp.md)|
