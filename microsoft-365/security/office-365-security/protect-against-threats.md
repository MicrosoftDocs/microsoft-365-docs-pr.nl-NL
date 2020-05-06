---
title: Beveiligen tegen bedreigingen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Meer informatie over de bescherming van bedreigingen in Office 365 en configureren hoe u deze voor uw organisatie gebruiken.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bdc7d619f3c48318572116fbc52647a0858ec5e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033888"
---
# <a name="protect-against-threats"></a>Beveiligen tegen bedreigingen

Microsoft 365 bevat een verscheidenheid aan functies voor bedreigingsbescherming. Hier is een handleiding voor snel starten die u gebruiken als checklist om ervoor te zorgen dat uw functies voor bedreigingsbescherming zijn ingesteld voor uw organisatie. Als u nieuw bent in functies voor bedreigingsbeveiliging in Office 365 of als u niet zeker weet waar u moet beginnen, gebruikt u de volgende richtlijnen als uitgangspunt.

> [!IMPORTANT]
> **De eerste aanbevolen instellingen zijn opgenomen voor elk type beleid; er zijn echter veel opties beschikbaar en u uw instellingen aanpassen aan de behoeften van uw specifieke organisatie.** Geef uw beleid of wijzigingen ongeveer 30 minuten de tijd om zich een weg te banen door uw datacenter.

## <a name="requirements"></a>Vereisten

### <a name="subscriptions"></a>Abonnementen

Functies voor bedreigingsbescherming zijn opgenomen in alle Microsoft 365-abonnementen; Sommige abonnementen bevatten echter meer geavanceerde functies. In de volgende tabel worden de beveiligingsfuncties in dit artikel weergegeven, samen met de minimale abonnementsvereisten.<br/>

|||
|---|---|
|**Beschermingstype**|**Abonnementsvereiste**|
|Beveiliging tegen malware|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)|
|Bescherming tegen schadelijke URL's en bestanden in e-mail- en Office-documenten|[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)|
|Bescherming tegen phishing|[Eop](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|Geavanceerde bescherming tegen phishing|[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Beveiliging tegen ongewenste e-mail|[Eop](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|Automatische zuivering van nul uur (voor e-mail)|[Eop](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)|
|Controlelogboekregistratie (dit wordt gebruikt voor rapportagedoeleinden)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>Rollen en machtigingen

U moet een geschikte rol toegewezen krijgen om beleid te configureren in het [Security & Compliance Center.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) De volgende tabel bevat enkele voorbeelden:

|Rol of rollengroep|Waar u meer leren|
|---------|---------|
|globale beheerder|[Over Microsoft 365-beheersrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Beveiligingsbeheerder|[Machtigingen voor beheerdersrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online Organisatiebeheer|[Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>En<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|

Zie [Machtigingen in het Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie.

## <a name="part-1---anti-malware-protection"></a>Deel 1 - Bescherming tegen malware

[Anti-malware bescherming](anti-malware-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)bevatten.

1. Kies in het [Security & Compliance Center](https://protection.office.com)de optie Threat **management** > **Policy** > **Anti-malware**.

2. Dubbelklik op het **standaardbeleid** en kies **instellingen**.

3. Geef de volgende instellingen op:

    - Houd in de sectie **Reactie op malwaredetectie** de standaardinstelling **Nr.**

    - Kies in de sectie **Common Attachment Types Filter** de optie **Op**.

4. Klik op **Opslaan**.

Zie Beleid voor antimalware configureren voor meer informatie over beleidsopties voor [antimalware.](configure-anti-malware-policies.md)

## <a name="part-2---protection-from-malicious-urls-and-files"></a>Deel 2 - Bescherming tegen schadelijke URL's en bestanden

Time-of-click bescherming tegen schadelijke URL's en bestanden is beschikbaar in abonnementen die [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) bevatten en is ingesteld via [ATP Safe Attachments](atp-safe-attachments.md) en [ATP Safe Links-beleid.](atp-safe-links.md)

### <a name="atp-safe-attachments-policies"></a>Beleid voor veilige bijlagen van ATP

Als u [ATP Safe Attachments](atp-safe-attachments.md)wilt instellen, moet u ten minste één ATP-beleid voor veilige bijlagen definiëren.

1. Kies [in](https://protection.office.com)het Security & Compliance Center de optie**Policy** > **ATP-veilige bijlagen**voor **beleid voor bedreigingen** > .

2. Selecteer de optie **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams**.

3. Klik in de sectie **E-mailbijlagen** **+** beveiligen op het plusteken ( ).

4. Geef de volgende instellingen op:

   - Typ **Name** in het `Block malware`vak Naam .

   - Kies **Blokkeren**in de sectie Antwoord .

   - Selecteer in de sectie **Bijlage omleiden** de optie **Omleiding inschakelen**en geef vervolgens het e-mailadres op voor de beveiligingsbeheerder of -operator van uw organisatie die gedetecteerde bestanden controleert.

   - Kies **Het** **geadresseerdendomein is**in de sectie Toegepast op . Selecteer vervolgens uw domein, kies **Toevoegen**en klik op **OK**.

5. Klik op **Opslaan**.

6. (**Aanbevolen extra stap**) Als globale beheerder of SharePoint Online-beheerder voert u de **[cmdlet Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uit met de parameter **DisallowInfectedFileDownload** die is ingesteld op *true* voor uw Microsoft 365-omgeving. (Dit voorkomt dat mensen bestanden openen, verplaatsen, kopiëren of delen die als kwaadaardig worden gedetecteerd.)

Zie Office [365 ATP-beleid voor veilige bijlagen instellen](set-up-atp-safe-attachments-policies.md) en Office [365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>Beleid voor veilige links van ATP

Als u [ATP Safe Links wilt](atp-safe-links.md)instellen, controleert en bewerkt u uw standaardbeleid en voegt u een beleid toe voor specifieke gebruikers.

1. Kies [in](https://protection.office.com)het Security & Compliance Center de optie Atp Safe > **Links** **voor bedreigingsbeheerbeleid** > **Policy**.

2. Dubbelklik op het **standaardbeleid.**

3. Selecteer **in** de sectie Veilige koppelingen gebruiken in de optie Microsoft **365 Apps voor bedrijven, Office voor iOS en Android**en klik op **Opslaan**.

4. Klik **in de sectie Beleid dat van toepassing is op specifieke ontvangers** op het plusteken (**+**).

5. Geef de volgende instellingen op:

   - Typ in het vak **Naam** een `Safe Links`naam, zoals .

   - Kies in de sectie **De actie selecteren de** optie **Aan**.

   - Selecteer de volgende opties:

     - **Veilige bijlagen gebruiken om downloadbare inhoud te scannen**

     - **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden**

     - **Laat gebruikers niet door veilige links naar de oorspronkelijke URL klikken**

   - Kies **Het** **geadresseerdendomein is**in de sectie Toegepast op . Selecteer vervolgens uw domein, kies **Toevoegen**en klik op **OK**.

6. Klik op **Opslaan**.

Zie [Beleid voor veilige koppelingen in ATP instellen in Office 365](set-up-atp-safe-links-policies.md) voor meer informatie.

## <a name="part-3---anti-phishing-protection"></a>Deel 3 - Bescherming tegen phishing

[Anti-phishing]

[Bescherming tegen phishing](anti-phishing-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)bevatten. Geavanceerde bescherming tegen phishing is beschikbaar in [ATP.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

In de volgende procedure wordt beschreven hoe u een ATP-antiphishingbeleid configureert. De stappen zijn vergelijkbaar voor het configureren van een anti-phishing beleid (zonder ATP).

1. Kies [in](https://protection.office.com)het Security & Compliance Center de optie Threat **management** > **Policy** > **ATP anti-phishing**.

2. Klik **op Standaardbeleid**.

3. Klik **in** de sectie Imitatie op **Bewerken**en geef de volgende instellingen op:

   - Schakel op het tabblad **Gebruikers toevoegen om het** tabblad te beschermen in. Voeg vervolgens gebruikers toe, zoals de leden van uw organisatie, uw CEO, CFO en andere senior leiders. (U een individueel e-mailadres typen of klikken om een lijst weer te geven.)

   - Schakel op het tabblad **Domeinen toevoegen om te beschermen** automatisch de domeinen in die ik **bezit.** Als u aangepaste domeinen hebt, voegt u deze ook toe.

   - Selecteer op het tabblad **Acties** de optie **Het bericht in quarantaine plaatsen** voor zowel de **nagebootste gebruiker** als de **nagebootste domeinopties.** Schakel bovendien veiligheidstips voor imitatie in.

   - Controleer op het tabblad **Postvakintelligentie** of postvakinformatie is ingeschakeld. Schakel bovendien op basis van de bescherming van postvakintelligentie op basis van imitatie in. Kies in de **lijst Als-e-mail wordt verzonden door een nagebootste gebruikerslijst** de optie **Het bericht in quarantaine plaatsen.**

   - Geef op het tabblad **Vertrouwde afzenders en domeinen toevoegen** alle vertrouwde afzenders of domeinen op die u wilt toevoegen.

   - Klik op het tabblad **Instellingen controleren** nadat u uw instellingen hebt gecontroleerd op **Opslaan**.

4. Klik in de sectie **Spoof** op **Bewerken**en geef de volgende instellingen op:

   - Controleer op het tabblad **Instellingen voor spoofing-filterinstellingen** of anti-spoofing-beveiliging is ingeschakeld.

   - Kies op het tabblad **Acties** de optie **Het bericht in quarantaine**plaatsen .

   - Klik op het tabblad **Instellingen controleren** nadat u uw instellingen hebt gecontroleerd op **Opslaan**. (Als u geen wijzigingen hebt aangebracht, klikt u op **Annuleren**.)

5. Sluit de pagina standaardbeleidsinstellingen.

Zie [ATP-beleid voor phishing configureren in Office 365](configure-atp-anti-phishing-policies.md)voor meer informatie over de anti-phishingbeleidsopties.

## <a name="part-4---anti-spam-protection"></a>Deel 4 - Bescherming tegen spam

[Bescherming tegen spam](anti-spam-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)bevatten.

1. Kies in het [Security & Compliance Center](https://protection.office.com)de optie **Bedreigingsbeheer** > **Anti-spam****Policy** > .

2. Schakel op het tabblad **Aangepast** **aangepaste instellingen** in.

3. Standaardbeleid **voor spamfilters**uitvouwen, op **Beleid bewerken**klikken en vervolgens de volgende instellingen opgeven:

   - Stel in de sectie **Spam- en bulkacties** de drempelwaarde in op een waarde van 5 of 6.

   - Controleer in de sectie Lijsten toestaan de toegestane afzenders en domeinen.In the **Allow lists** section, review (and if necessary, edit) your llowed senders and domains.

4. Klik op **Opslaan**.

Zie [Beleid voor antispam configureren in Office 365](configure-your-spam-filter-policies.md)voor meer informatie over de opties voor antispambeleid.

## <a name="part-5---additional-settings-to-configure"></a>Deel 5 - Extra instellingen om te configureren

Naast het configureren van bescherming tegen malware, schadelijke URL's en bestanden, phishing en spam, raden we u aan uw instellingen voor automatische controle en controle van nul uur te configureren.

### <a name="zero-hour-auto-purge-for-email"></a>Nuluur automatische zuivering voor e-mail

[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)bevatten. Deze beveiliging is standaard ingeschakeld; er moet echter aan de volgende voorwaarden worden voldaan om de bescherming van kracht te kunnen hebben:

- Spamacties zijn ingesteld op **Bericht verplaatsen naar de map Ongewenste e-mail** in [antispambeleid.](anti-spam-protection.md)

- Gebruikers hebben hun standaard [instellingen voor ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)behouden en hebben de beveiliging van ongewenste e-mail niet uitgeschakeld.

Zie [Zero-hour auto purge voor](zero-hour-auto-purge.md)meer informatie - bescherming tegen spam en malware .

### <a name="audit-logging-for-reporting-and-investigation"></a>Controlelogboekregistratie voor rapportage en onderzoek

Controlelogboekregistratie is beschikbaar in abonnementen die [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)bevatten. Als u gegevens wilt weergeven in meldingen van bedreigingsbeveiliging, zoals het [beveiligingsdashboard,](security-dashboard.md) [e-mailbeveiligingsrapporten](view-email-security-reports.md)en [Explorer,](threat-explorer.md)moet controlelogboekregistratie voor uw organisatie worden ingeschakeld. Zie [Zoeken in het controlelogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.

## <a name="post-setup-tasks"></a>Taken na het instellen

Nadat u uw functies voor bedreigingsbeveiliging hebt geconfigureerd, moet u controleren hoe deze functies werken, uw beleid bekijken en zo nodig herzien en op nieuwe functies en service-updates letten.

|||
|---|---|
|**Wat te doen**|**Informatiebronnen**|
|Bekijk hoe functies voor bedreigingsbescherming voor uw organisatie werken door rapporten te bekijken|[Beveiligingsdashboard](security-dashboard.md)<br/>[Beveiligingsrapporten per e-mail](view-email-security-reports.md)<br/>[Rapporten voor Office 365 ATP](view-reports-for-atp.md)<br/>[Bedreigingsverkenner](threat-explorer.md)|
|Uw beleid voor bedreigingsbescherming regelmatig controleren en herzien als dat nodig is|[Secure Score](../mtp/microsoft-secure-score.md)<br/>[Slimme rapporten en inzichten](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 threat investigation and response features Microsoft 365 threat investigation and response features Microsoft 365 threat investigation and response features Microsoft 3](keep-users-safe-with-office-365-ti.md)|
|Kijk uit voor nieuwe functies en service-updates|[Standaard- en gerichte releaseopties](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[Berichtencentrum](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[Microsoft 365-roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Servicebeschrijvingen](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
