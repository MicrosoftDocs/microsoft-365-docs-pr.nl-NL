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
ms.openlocfilehash: 4c32026ab4f33a68b1f63cb000807671839f6bad
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821281"
---
# <a name="protect-against-threats"></a>Beveiligen tegen bedreigingen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Hier is een snelstarthandleiding die de configuratie van Defender voor Office 365 in segmenten opbreekt. Als u nog niet bekend bent met functies voor bedreigingsbeveiliging in Office 365, weet u niet waar u moet beginnen of als u het beste leert door te *doen,* gebruikt u deze richtlijnen als controlelijst en uitgangspunt.

> [!IMPORTANT]
> **De eerste aanbevolen instellingen zijn opgenomen voor** elk type beleid. Er zijn echter veel opties beschikbaar en u kunt uw instellingen aanpassen aan de behoeften van uw specifieke organisatie. Sta ongeveer 30 minuten toe dat uw beleid of wijzigingen hun weg vinden in uw datacenter.

## <a name="requirements"></a>Vereisten

### <a name="subscriptions"></a>Abonnementen

Bedreigingsbeveiligingsfuncties zijn opgenomen in *alle* Microsoft- of Office 365-abonnementen; Sommige abonnementen hebben echter geavanceerde functies. De onderstaande tabel bevat de beveiligingsfuncties in dit artikel samen met de minimale abonnementsvereisten.

> [!TIP]
> Buiten de aanwijzingen voor het in-  en uit- of in- en uit-/uit- stappen start u anti-malware, anti-phishing en antispam, die zijn gemarkeerd als onderdeel van Office 365 Exchange Online Protection **(EOP).** Dit kan vreemd lijken in een Defender voor Office 365 artikel, totdat u eraan herinnert (**Defender voor** Office 365 ) EOP bevat en verder bouwt.

<br>

****

|Beveiligingstype|Abonnementsvereiste|
|---|---|
|Auditregistratie (voor rapportagedoeleinden)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Beveiliging tegen malware|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Bescherming tegen phishing|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Beveiliging tegen ongewenste e-mail|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Auto purge van nul uur (voor e-mail)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Bescherming tegen schadelijke URL's en bestanden in e-mail en Office documenten (Safe Koppelingen en Safe bijlagen)|[Microsoft Defender voor Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|De Safe bijlagen in SharePoint, OneDrive en Microsoft Teams werkbelastingen|[Microsoft Defender voor Office 365](turn-on-mdo-for-spo-odb-and-teams.md)|
|Geavanceerde anti-phishingbeveiliging|[Microsoft Defender voor Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Rollen en machtigingen

Als u Defender wilt configureren Office 365 beleidsregels, moet u een passende rol krijgen toegewezen in het [beveiligings- & compliancecentrum.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) Bekijk de onderstaande tabel voor rollen die deze acties kunnen uitvoeren.

<br>

****

|Rol of rollengroep|Waar kunt u meer informatie?|
|---|---|
|globale beheerder|[Over Microsoft 365-beheersrollen](../../admin/add-users/about-admin-roles.md)|
|Beveiligingsbeheerder|[Machtigingen voor beheerdersrollen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online Organisatiebeheer|[Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) <p> en <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|

Zie Machtigingen in het Beveiligings- & [compliancecentrum voor meer informatie.](permissions-in-the-security-and-compliance-center.md)

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>Auditlogregistratie inschakelen voor rapportage en onderzoek

- Begin de auditregistratie eerder. U moet controleren om aan te zijn **voor** een aantal van de volgende stappen. Auditregistratie is beschikbaar in abonnementen met [Exchange Online.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) Als u gegevens wilt weergeven in bedreigingsbeveiligingsrapporten, zoals het beveiligingsdashboard, [](security-dashboard.md)e-mailbeveiligingsrapporten [en](view-email-security-reports.md) [Verkenner,](threat-explorer.md)moet auditregistratie zijn *aan.* Zie Zoeken in auditlogboek in- [of uitschakelen voor meer informatie.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>Deel 1 - Bescherming tegen malware in EOP

Zie [EOP anti-malwarebeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)voor meer informatie over de aanbevolen instellingen voor anti-malware.

1. Openen <https://security.microsoft.com/antimalwarev2> .

2. Selecteer op **de pagina Anti-malware** het beleid Met de naam **Standaardbeleid** door op de naam te klikken.

3. Klik in het flyout met beleidsdetails dat wordt geopend op **Beveiligingsinstellingen bewerken** en configureer de volgende instellingen:
   - Selecteer **Het filter algemene bijlagen inschakelen om** het algemene bijlagefilter in te stellen. Klik **op Bestandstypen aanpassen** om meer bestandstypen toe te voegen.
   - Controleer of **Automatisch verwijderen van nul uur inschakelen voor malware** is geselecteerd.
   - Controleer of geen van de instellingen in de sectie **Melding** is geselecteerd.

   Klik op **Opslaan** wanneer u gereed bent.

4. Klik in de flyout met beleidsdetails weer op **Sluiten**.

Zie Anti-malwarebeleid configureren in EOP voor gedetailleerde instructies voor het configureren van [anti-malwarebeleid.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>Deel 2 - Bescherming tegen phishing in EOP en Defender voor Office 365

[Anti-phishingbeveiliging](anti-phishing-protection.md) is beschikbaar in abonnementen met [EOP.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Geavanceerde anti-phishingbeveiliging is beschikbaar in [Defender voor Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

Zie [EOP anti-phishingbeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) en [Anti-phishingbeleidsinstellingen in Microsoft Defender](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)voor Office 365 voor meer informatie over de aanbevolen instellingen voor anti-phishingbeleid.

In de volgende procedure wordt beschreven hoe u het standaard anti-phishingbeleid configureert. Instellingen die alleen beschikbaar zijn in Defender voor Office 365 zijn duidelijk gemarkeerd.

1. Openen <https://security.microsoft.com/antiphishing> .

2. Selecteer op **de pagina Anti-phishing** het beleid met de naam **Office365 AntiPhish Default (Standaard)** door op de naam te klikken.

3. Configureer de volgende instellingen in de flyout beleidsdetails die worden weergegeven:

   - **Phishingdrempel & beveiligingssectie:** Klik op **Beveiligingsinstellingen bewerken** en  configureer de volgende instellingen in het fly-out Beveiligingsinstellingen bewerken dat wordt geopend:
     - **Drempelwaarde voor** <sup>\*</sup> phishing-e-mail: Selecteer **2 - Agressief** (standaard) of **3 - Agressiever** (strikt).
     - **Sectie Imitatie:** <sup>\*</sup> De volgende waarden configureren:
       - Selecteer **Gebruikers inschakelen** om te beveiligen, klik op de koppeling **Afzender(s) beheren (nn)** die wordt weergegeven en voeg vervolgens interne en externe afzenders toe om zich te beschermen tegen imitatie, zoals de bestuursleden van uw organisatie, uw CEO, CFO en andere senior leaders.
       - Selecteer **Domeinen beveiligen inschakelen** en configureer de volgende instellingen die worden weergegeven:
         - Selecteer **Domeinen opnemen die ik bezit** om interne afzenders in uw geaccepteerde domeinen te beschermen (zichtbaar door te klikken op **Mijn** domeinen weergeven) tegen imitatie.
         - Als u afzenders in andere domeinen wilt beveiligen, selecteert u Aangepaste domeinen **opnemen,** klikt u op de koppeling Aangepaste **domein(nn) beheren (nn)** die wordt weergegeven en voegt u vervolgens andere domeinen toe om zich te beschermen tegen imitatie.
     - Sectie Vertrouwde **afzenders** en domeinen toevoegen: Klik op Vertrouwde <sup>\*</sup> **afzender(s) en domeinen (nn)** beheren om indien nodig uitzonderingen op afzender- en afzenderdomeinen te configureren voor imitatiebeveiliging.
     - Instellingen voor postvakinformatie: Controleer of Postvakintelligentie inschakelen en <sup>\*</sup> **Intelligence inschakelen voor imitatiebeveiliging** zijn geselecteerd. 
     - **Sectie Spoof:** Controleren **Of spoofinformatie inschakelen** is geselecteerd.

     Klik op **Opslaan** wanneer u gereed bent.

   - **Sectie** Acties: Klik op **Acties bewerken** en configureer de volgende instellingen in **het** fly-out Acties bewerken dat wordt geopend:
     - **Sectie Berichtacties:** De volgende instellingen configureren:
       - **Als bericht wordt gedetecteerd als een nagebootsde gebruiker:** <sup>\*</sup> Selecteer Het bericht in quarantaine **plaatsen.**
       - **Als bericht wordt gedetecteerd als een nagebootsd domein:** <sup>\*</sup> Selecteer Het bericht in quarantaine **plaatsen.**
       - **Als postvakinformatie een** nagebootste gebruiker detecteert: Selecteer Bericht verplaatsen naar de mappen Ongewenste e-mail van de geadresseerden (Standaard) of Het bericht in quarantaine plaatsen <sup>\*</sup> (Strikt).  
       - **Als bericht wordt gedetecteerd als spoof:** Selecteer **Bericht verplaatsen** naar de mappen ongewenste e-mail van de geadresseerden (Standaard) of **Het** bericht in quarantaine plaatsen (Strikt).
     - **Veiligheidstips & de sectie** Indicatoren: De volgende instellingen configureren:
       - **Gebruikers imiteren veiligheidstip** <sup>\*</sup> : Selecteren (in- of uit).
       - **Domein-imitatie veiligheidstip** <sup>\*</sup> : Selecteren (in- of uit).
       - **Ongebruikelijke tekens voor gebruikers imiteren veiligheidstip** <sup>\*</sup> : Selecteren (in- of uit).
       - **Show (?) for unauthenticated senders for spoof**: Select (turn on).
       - **Tag 'via' laten** zien: Selecteer (in) als deze instelling beschikbaar is.

     Klik op **Opslaan** wanneer u gereed bent.

   <sup>\*</sup>Deze instelling is alleen beschikbaar in Defender voor Office 365.

4. Klik **op Opslaan** en klik vervolgens op **Sluiten**

Zie [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md) en [Anti-phishingbeleid configureren in Microsoft Defender](configure-atp-anti-phishing-policies.md)voor meer informatie over het configureren van anti-phishingbeleid Office 365.

## <a name="part-3---anti-spam-protection-in-eop"></a>Deel 3 - Bescherming tegen spam in EOP

Zie [EOP antispambeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)voor meer informatie over de aanbevolen instellingen voor antispam.

1. Openen <https://security.microsoft.com/antispam> .

2. Selecteer op **de pagina Antispambeleid** het beleid **antispambeleid (standaard) in** de lijst door op de naam te klikken.

3. Ga als volgt te werk in de flyout beleidsdetails die worden weergegeven:
   - **Bulk e-maildrempel & sectie spameigenschappen:** Klik op Drempelwaarde en eigenschappen **voor spam bewerken.** Stel in **de flyout** voor spam en  eigenschappen die worden weergegeven, de drempelwaarde voor bulksgewijs e-mail in op 5 (Strikt) of 6 (standaard). Klik op **Opslaan** wanneer u gereed bent.
   - **Sectie Toegestane en geblokkeerde afzenders en** domeinen: Controleer of bewerk uw toegestane afzenders en toegestane domeinen.

4. Klik op **Sluiten** wanneer u gereed bent.

Zie Antispambeleid configureren in EOP voor gedetailleerde instructies voor het configureren van [antispambeleid.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Deel 4 - Bescherming tegen schadelijke URL's en bestanden (Safe Koppelingen en Safe bijlagen in Defender voor Office 365)

Time-of-click-beveiliging tegen schadelijke URL's en bestanden is beschikbaar in abonnementen met Microsoft Defender voor [Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) Het is ingesteld via het [Safe bijlagen en](safe-attachments.md) Safe [koppelingenbeleid.](safe-links.md)

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Safe Bijlagenbeleid in Microsoft Defender voor Office 365

Als u Safe bijlagen wilt [instellen,](safe-attachments.md)maakt u ten minste één Safe koppelingenbeleid.

1. Kies in [& Beveiligingscentrum](https://protection.office.com)de optie **ATP** voor \>  \> **bedreigingsbeheerbeleid Safe Bijlagen** en klik vervolgens op **Maken.**

2. Configureer **de volgende Safe in** de wizard Nieuw Safe bijlagenbeleid dat wordt weergegeven:

   - Typ in **het** vak Naam `Block malware` en klik vervolgens op **Volgende.**

   - Configureer **op Instellingen** pagina de volgende instellingen:
     - Kies in **Safe sectie Onbekende malwarereactie** de optie **Blokkeren.**
     - Selecteer in **de sectie Bijlage** omleiden de optie **Omleiding inschakelen.** Geef het e-mailadres op voor de beveiligingsbeheerder of operator van uw organisatie, die gedetecteerde bestanden controleert.

     Klik op **Volgende**.

3. Klik op **de** pagina Toegepast op Een voorwaarde **toevoegen,** kies Toegepast als: Het domein van de geadresseerde **is,** klik op **Toevoegen,** selecteer uw domein of domeinen, klik op **Toevoegen,** klik op **Klaar** en klik vervolgens op **Volgende.**

4. Controleer de instellingen en klik vervolgens op **Voltooien.**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Safe Beleidsregels voor koppelingen in Microsoft Defender voor Office 365

Als u Safe [koppelingen](safe-links.md)wilt instellen, bekijkt en bewerkt u de algemene instellingen voor Safe koppelingen en maakt u ten minste één Safe koppelingenbeleid.

1. Kies in [& Beveiligingscentrum](https://protection.office.com)de  optie \>  \> **ATP-Safe-koppelingen** voor bedreigingsbeleid en klik op **Algemene** instellingen en configureer vervolgens de volgende instellingen:

   - Controleer **Gebruik Safe koppelingen in: Office 365 is** ingeschakeld: ![ Schakel ](../../media/scc-toggle-on.png) in.
   - **Houd niet bij wanneer gebruikers op Safe Koppelingen** klikken: Schakel deze instelling uit om klikken van gebruikers bij te houden: Schakelen ![ ](../../media/scc-toggle-off.png) uit.
   - **Laat gebruikers niet door veilige koppelingen naar de oorspronkelijke URL** klikken: Controleer of deze instelling is ingeschakeld: Schakel ![ ](../../media/scc-toggle-on.png) in.

   Klik op **Opslaan** wanneer u gereed bent.

2. Klik op de hoofdpagina Safe koppelingen op **Maken.**

3. Configureer **de volgende instellingen Safe** de wizard Beleid maken Safe koppelingen die wordt weergegeven:

   - Typ in **het** vak Naam een naam, zoals `Safe Links` , en klik vervolgens op **Volgende.**

   - Configureer **op Instellingen** pagina de volgende instellingen:
     - **Selecteer de actie voor onbekende potentieel schadelijke URL's in berichten:** Kies **Aan.**
     - Selecteer de actie voor onbekende of potentieel schadelijke **URL's binnen Microsoft Teams**: Kies **Aan.**
     - **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie zijn verzonden**
     - **Wacht totdat URL-scannen is voltooid voordat u het bericht bezorgt**
     - **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie zijn verzonden**
     - **Gebruikers niet toestaan door te klikken naar de oorspronkelijke URL**

     Klik op **Volgende**.

4. Klik op **de** pagina Toegepast op Een voorwaarde **toevoegen,** kies Toegepast als: Het domein van de geadresseerde **is,** klik op **Toevoegen,** selecteer uw domein of domeinen, klik op **Toevoegen,** klik op **Klaar** en klik vervolgens op **Volgende.**

5. Controleer de instellingen en klik vervolgens op **Voltooien.**

Zie [Beleid voor veilige koppelingen instellen](set-up-safe-links-policies.md) voor meer informatie.

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Deel 5 - Controleren Safe bijlagen voor SharePoint, OneDrive en Microsoft Teams is ingeschakeld

Werkbelastingen zoals SharePoint, OneDrive en Teams zijn gemaakt voor samenwerking. Het gebruik van Defender Office 365 helpt bij het blokkeren en opsporen van bestanden die zijn geïdentificeerd als schadelijk in teamsites en documentbibliotheken. U kunt hier meer lezen over hoe dat [werkt.](mdo-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> **Voordat u deze procedure start, moet u controleren of auditregistratie al is ingeschakeld voor uw Microsoft 365 omgeving.** Dit wordt meestal gedaan door iemand die de rol Auditlogboeken heeft toegewezen in Exchange Online. Zie Zoeken in [auditlogboek in- of uitschakelen voor meer informatie.](../../compliance/turn-audit-log-search-on-or-off.md)

1. Kies in [& Beveiligingscentrum](https://protection.office.com)de optie **ATP** voor \>  \> **bedreigingsbeheerbeleid Safe Bijlagen** en klik vervolgens op Algemene **instellingen.**

2. Controleer of de schakelknop Defender in Office 365 voor **SharePoint, OneDrive** en Microsoft Teams aan de rechterkant staat: Schakel De schakelknop in en klik vervolgens op ![ ](../../media/scc-toggle-on.png) **Opslaan.**

3. Controleer (en bewerk zo nodig) [](set-up-safe-attachments-policies.md) het beleid voor bijlagen Safe uw organisatie en Safe [koppelingen.](set-up-safe-links-policies.md)

4. (Aanbevolen) Als globale beheerder of SharePoint Online-beheerder kunt u de cmdlet **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** uitvoeren met de parameter _DisallowInfectedFileDownload_ ingesteld op `$true` .

   - `$true` blokkeert alle acties (behalve Verwijderen) voor gedetecteerde bestanden. Personen kunnen gedetecteerde bestanden niet openen, verplaatsen, kopiëren of delen.
   - `$false` blokkeert alle acties, behalve Verwijderen en Downloaden. Personen kunnen ervoor kiezen om het risico te accepteren en een gedetecteerd bestand te downloaden.

   > [!TIP]
   > Zie Beheer Microsoft 365 met PowerShell voor meer Microsoft 365 over het gebruik van PowerShell met [Microsoft 365.](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)

5. U kunt maximaal 30 minuten toestaan dat uw wijzigingen worden verspreid naar alle Microsoft 365 datacenters.

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
>- [Gebruik het beveiligingscentrum om in quarantaine geplaatste bestanden te beheren in Defender voor Office 365](manage-quarantined-messages-and-files.md#use-the-security-center-to-manage-quarantined-files-in-defender-for-office-365)
>- [Wat moet u doen als er een schadelijk bestand wordt gevonden in SharePoint Online, OneDrive of Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [In quarantaine geplaatste berichten en bestanden beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Deel 6 - Aanvullende instellingen om te configureren

Naast het configureren van beveiliging tegen malware, schadelijke URL's en bestanden, phishing en spam, raden we u aan om automatische 0-uurs purge te configureren.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Auto purge van nul uur voor e-mail in EOP

[Zap (Zero Hour Auto Purge)](zero-hour-auto-purge.md) is beschikbaar in abonnementen met [EOP.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Deze beveiliging is standaard ingeschakeld. Aan de volgende voorwaarden moet echter worden voldaan om de beveiliging van kracht te laten zijn:

- Spamacties zijn ingesteld op **Bericht verplaatsen naar map Ongewenste e-mail** in [antispambeleid.](anti-spam-protection.md)

- Gebruikers hebben hun standaardinstellingen voor ongewenste [e-mail behouden](configure-junk-email-settings-on-exo-mailboxes.md)en hebben de beveiliging van ongewenste e-mail niet uitgeschakeld.

Zie [Zero-hour Auto Purge - bescherming tegen spam en malware](zero-hour-auto-purge.md)voor meer informatie.

## <a name="post-setup-tasks-and-next-steps"></a>Taken na installatie en volgende stappen

Controleer na het configureren van de functies voor bedreigingsbeveiliging hoe deze functies werken. Controleer en wijzig uw beleid, zodat ze doen wat u nodig hebt. Let ook op nieuwe functies en service-updates die waarde kunnen toevoegen.

****

|Wat moet u doen?|Informatiebronnen|
|---|---|
|Bekijk hoe functies voor bedreigingsbeveiliging voor uw organisatie werken door rapporten te bekijken|[Beveiligingsdashboard](security-dashboard.md) <p> [E-mailbeveiligingsrapporten](view-email-security-reports.md) <p> [Rapporten voor Microsoft Defender voor Office 365](view-reports-for-mdo.md) <p> [Bedreigingsverkenner](threat-explorer.md)|
|Controleer uw beleid voor bedreigingsbeveiliging regelmatig en wijzig deze zo nodig|[Secure Score](../defender/microsoft-secure-score.md) <p> [Slimme rapporten en inzichten](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 functies voor bedreigingsonderzoek en -antwoord](./office-365-ti.md)|
|Nieuwe functies en service-updates bekijken|[Standaard- en targeted releaseopties](../../admin/manage/release-options-in-office-365.md) <p> [Berichtencentrum](../../admin/manage/message-center.md) <p> [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Servicebeschrijvingen](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Meer informatie over aanbevolen standaard- en strikte beveiligingsconfiguraties voor EOP en Defender voor Office 365|[Aanbevolen instellingen voor EOP en Microsoft Defender voor Office 365 beveiliging](recommended-settings-for-eop-and-office365.md)|
