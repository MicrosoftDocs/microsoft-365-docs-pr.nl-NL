---
title: Beveiligen tegen bedreigingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
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
description: Beheerders kunnen meer te weten komen over bedreigingsbeveiliging in Microsoft 365 en configureren hoe deze voor uw organisatie kunnen worden gebruikt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 54500500095392ebfc3d93080701fa4715fc8448
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617394"
---
# <a name="protect-against-threats"></a>Beveiligen tegen bedreigingen

Microsoft 365 bevat een verscheidenheid aan functies voor bedreigingsbescherming. Hier is een handleiding die u gebruiken als checklist om ervoor te zorgen dat uw functies voor bedreigingsbescherming zijn ingesteld voor uw organisatie. Als u de functies voor bedreigingsbeveiliging in Office 365 nieuw bent of als u niet zeker weet waar u moet beginnen, gebruikt u de volgende richtlijnen als uitgangspunt.

> [!IMPORTANT]
> **Initiële aanbevolen instellingen zijn inbegrepen voor elk soort beleid; er zijn echter veel opties beschikbaar en u uw instellingen aanpassen aan de behoeften van uw specifieke organisatie.** Sta ongeveer 30 minuten toe voor uw beleid of wijzigingen om zich een weg te banen door uw datacenter.

## <a name="requirements"></a>Vereisten

### <a name="subscriptions"></a>Abonnementen

Functies voor bedreigingsbescherming zijn opgenomen in alle Microsoft 365-abonnementen; Sommige abonnementen bevatten echter meer geavanceerde functies. In de volgende tabel vindt u de beveiligingsfuncties in dit artikel samen met de minimale abonnementsvereisten.<br/>

|||
|---|---|
|**Beveiligingstype**|**Abonnementsvereiste**|
|Beveiliging tegen malware|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)|
|Bescherming tegen schadelijke URL's en bestanden in e-mail- en Office-documenten|[Atp (Advanced Threat Protection) voor Office 365 (Advanced Threat Protection)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Bescherming tegen phishing|[Eop](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Geavanceerde bescherming tegen phishing|[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Beveiliging tegen ongewenste e-mail|[Eop](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Zero-hour automatische zuivering (voor e-mail)|[Eop](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Controlelogboekregistratie (dit wordt gebruikt voor rapportagedoeleinden)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>Rollen en machtigingen

U moet een geschikte rol toegewezen krijgen om beleid te configureren in het [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). De volgende tabel bevat enkele voorbeelden:

|Rol of rollengroep|Waar meer informatie te leren|
|---------|---------|
|globale beheerder|[Over Microsoft 365-beheersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Beveiligingsbeheerder|[Machtigingen voor beheerdersrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online Organisatiebeheer|[Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>En<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Zie [Machtigingen in het Security &amp; Compliance Center voor](permissions-in-the-security-and-compliance-center.md)meer informatie.

## <a name="part-1---anti-malware-protection"></a>Deel 1 - Bescherming tegen malware

[Bescherming tegen malware](anti-malware-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.

1. Kies in het [Security & Compliance Center](https://protection.office.com)voor Threat **management**  >  **Policy**  >  **Anti-malware**.

2. Dubbelklik op het **standaardbeleid** en kies **instellingen**.

3. Geef de volgende instellingen op:

    - Houd in de sectie **Malwaredetectierespons** de standaardinstelling van **Nr.**

    - Kies in de sectie **Filter gemeenschappelijke bijlagetypen** de optie **Aan**.

4. Klik op **Opslaan**.

Zie [Anti-malwarebeleid configureren](configure-anti-malware-policies.md)voor meer informatie over beleidsopties voor malwarebestrijding.

## <a name="part-2---protection-from-malicious-urls-and-files"></a>Deel 2 - Bescherming tegen kwaadaardige URL's en bestanden

Tijd-van-klik bescherming tegen kwaadaardige URL's en bestanden is beschikbaar in abonnementen die [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) bevatten en is ingesteld via [ATP Safe Attachments](atp-safe-attachments.md) en [ATP Safe Links](atp-safe-links.md) beleid.

### <a name="atp-safe-attachments-policies"></a>Atp-beleid voor veilige bijlagen

Als u [ATP Safe Attachments](atp-safe-attachments.md)wilt instellen, moet u ten minste één ATP-beleid voor veilige bijlagen definiëren.

1. Kies in het [Security & Compliance Center](https://protection.office.com)de ATP-veilige bijlagen voor **bedreigingsbeheerbeleid**  >  **Policy**  >  **ATP safe attachments**.

2. Selecteer de optie **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams**.

3. Klik in de sectie **E-mailbijlagen beveiligen** op het plusteken ( **+** ).

4. Geef de volgende instellingen op:

   - Typ **in** het vak Naam `Block malware` .

   - Kies in de sectie Antwoord de optie **Blokkeren**.

   - Selecteer in de sectie **Bijlage Omleiden** de optie **Omleiding inschakelen**en geef vervolgens het e-mailadres op voor de beveiligingsbeheerder of -operator van uw organisatie die gedetecteerde bestanden controleert.

   - Kies **in** de sectie Toegepast op **de optie Het domein van de ontvanger is**. Selecteer vervolgens uw domein, kies **Toevoegen**en klik op **OK**.

5. Klik op **Opslaan**.

6. (**Aanbevolen extra stap**) Voer als globale beheerder of SharePoint Online-beheerder de cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** uit met de parameter **DisallowInfectedFileDownload** ingesteld op *true* voor uw Microsoft 365-omgeving. (Dit voorkomt dat mensen bestanden openen, verplaatsen, kopiëren of delen die als kwaadaardig worden gedetecteerd.)

Zie [Office 365 ATP Safe Attachments-beleid instellen](set-up-atp-safe-attachments-policies.md) en Office [365 ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams voor](turn-on-atp-for-spo-odb-and-teams.md)meer informatie.

### <a name="atp-safe-links-policies"></a>ATP Safe Links beleid

Als u [veilige verbindingsknopen ATP](atp-safe-links.md)wilt instellen, controleert en bewerkt u uw standaardbeleid en voegt u een beleid toe voor specifieke gebruikers.

1. Kies in het [Security & Compliance Center](https://protection.office.com)de ATP Safe Links voor **bedreigingsbeheerbeleid**  >  **Policy**  >  **ATP Safe Links**.

2. Dubbelklik op het **standaardbeleid.**

3. Selecteer in de sectie **Veilige koppelingen gebruiken in** de sectie De optie Microsoft **365 Apps voor bedrijven, Office voor iOS en Android**en klik vervolgens op **Opslaan**.

4. Klik in de sectie **Beleid dat van toepassing is op specifieke geadresseerden** op het plusteken ( **+** ).

5. Geef de volgende instellingen op:

   - Typ in het vak **Naam** een naam, zoals `Safe Links` .

   - Kies in **de sectie Selecteer de actie** de optie **Aan**.

   - Selecteer de volgende opties:

     - **Veilige bijlagen gebruiken om downloadbare inhoud te scannen**

     - **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden**

     - **Laat gebruikers niet doorklikken naar veilige links naar de oorspronkelijke URL**

   - Kies **in** de sectie Toegepast op **de optie Het domein van de ontvanger is**. Selecteer vervolgens uw domein, kies **Toevoegen**en klik op **OK**.

6. Klik op **Opslaan**.

Zie [Beleid voor veilige koppelingen in ATP instellen in Office 365](set-up-atp-safe-links-policies.md) voor meer informatie.

## <a name="part-3---anti-phishing-protection"></a>Deel 3 - Bescherming tegen phishing

[Anti-phishing]

[Bescherming tegen phishing](anti-phishing-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten. Geavanceerde anti-phishing bescherming is beschikbaar in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

In de volgende procedure wordt beschreven hoe u een ATP-antiphishingbeleid configureert. De stappen zijn vergelijkbaar voor het configureren van een anti-phishing beleid (zonder ATP).

1. Kies in het [Security & Compliance Center](https://protection.office.com)voor **Threat management**  >  **Policy**  >  **ATP-antiphishing**van bedreigingsbeheerbeleid .

2. Klik **op Standaardbeleid**.

3. Klik in de sectie **Imitatie** op **Bewerken**en geef vervolgens de volgende instellingen op:

   - Schakel op het tabblad **Gebruikers toevoegen om te beveiligen** de beveiliging in. Voeg vervolgens gebruikers toe, zoals de bestuursleden van uw organisatie, uw CEO, CFO en andere senior leiders. (U een individueel e-mailadres typen of klikken om een lijst weer te geven.)

   - Schakel op het tabblad **Domeinen toevoegen om te beveiligen** automatisch de **domeinen op die ik bezit.** Als u aangepaste domeinen hebt, voegt u deze ook toe.

   - Selecteer **op** het tabblad Handelingen **het bericht in quarantaine** plaatsen voor zowel de **geïmiteerde gebruiker als** de **geïmiteerde domeinopties.** Schakel bovendien impersonatieveiligheidstips in.

   - Controleer op het tabblad **Inlichtingendienst Postvak** of de inlichtingendienst is ingeschakeld. Schakel bovendien de op basis van postvakintelligentie op basis van imitatiebeveiliging in. Kies in de **e-mail als e-mail wordt verzonden door een geïmiteerde gebruikerslijst,** **de optie Het bericht in quarantaine**plaatsen .

   - Geef op het tabblad **Vertrouwde afzenders en domeinen toevoegen** alle vertrouwde afzenders of domeinen op die u wilt toevoegen.

   - Klik op het tabblad **Instellingen controleren** nadat u uw instellingen hebt gecontroleerd op **Opslaan.**

4. Klik in de sectie **Spoof** op **Bewerken**en geef de volgende instellingen op:

   - Controleer op het tabblad **Instellingen voor spoofingfilterinstellingen** of anti-spoofingbeveiliging is ingeschakeld.

   - Kies **op** het tabblad Handelingen **het bericht in quarantaine**.

   - Klik op het tabblad **Instellingen controleren** nadat u uw instellingen hebt gecontroleerd op **Opslaan.** (Als u geen wijzigingen hebt aangebracht, klikt u op **Annuleren**.)

5. Sluit de pagina standaardbeleidsinstellingen.

Zie [ATP-antiphishingbeleid configureren](configure-atp-anti-phishing-policies.md)voor meer informatie over uw anti-phishingbeleid.

## <a name="part-4---anti-spam-protection"></a>Deel 4 - Anti-spam bescherming

[Antispambeveiliging](anti-spam-protection.md) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten.

1. Kies in het [Security & Compliance Center](https://protection.office.com)voor Threat **management**  >  **Policy**  >  **Anti-spam**.

2. Schakel op het tabblad **Aangepast** **aangepaste instellingen** in.

3. Uitvouwen **Standaard spam filter beleid,** klik op **Beleid bewerken**, en geef vervolgens de volgende instellingen:

   - Stel in de sectie **Spam- en bulkacties** de drempel in op een waarde van 5 of 6.

   - Controleer (en bewerk) in de sectie **Lijsten toestaan** uw toegestane afzenders en domeinen indient (en indien nodig) bewerkt.

4. Klik op **Opslaan**.

Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)voor meer informatie over uw antispambeleidsopties.

## <a name="part-5---additional-settings-to-configure"></a>Deel 5 - Extra instellingen om te configureren

Naast het configureren van bescherming tegen malware, kwaadaardige URL's en bestanden, phishing en spam, raden we u aan uw instellingen voor automatische zuivering en controleregistratie van nul uur te configureren.

### <a name="zero-hour-auto-purge-for-email"></a>Zero-hour automatische zuivering voor e-mail

[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is beschikbaar in abonnementen die [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)bevatten. Deze beveiliging is standaard ingeschakeld. aan de volgende voorwaarden moet echter worden voldaan om de bescherming van kracht te maken:

- Spamacties zijn ingesteld op **Bericht verplaatsen naar map Ongewenste e-mail** in [antispambeleid.](anti-spam-protection.md)

- Gebruikers hebben hun standaard [instellingen voor ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)behouden en hebben de beveiliging van ongewenste e-mail niet uitgeschakeld.

Zie voor meer informatie [de automatische zuivering van zero-uur - bescherming tegen spam en malware.](zero-hour-auto-purge.md)

### <a name="audit-logging-for-reporting-and-investigation"></a>Controleregistratie voor rapportage en onderzoek

Controlelogboekregistratie is beschikbaar in abonnementen die [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)bevatten. Als u gegevens wilt weergeven in rapporten over bedreigingsbescherming, zoals het [beveiligingsdashboard,](security-dashboard.md) [e-mailbeveiligingsrapporten](view-email-security-reports.md)en [Explorer,](threat-explorer.md)moet controleregistratie zijn ingeschakeld voor uw organisatie. Zie [Zoeken in of uit controleren op controlelogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.

## <a name="post-setup-tasks"></a>Taken na het instellen

Nadat u uw functies voor bedreigingsbeveiliging hebt geconfigureerd, controleert u hoe deze functies werken, controleert en herziet u uw beleid indien nodig en kijkt u naar nieuwe functies en service-updates.

|||
|---|---|
|**Wat te doen**|**Informatiebronnen**|
|Bekijk hoe functies voor bedreigingsbescherming voor uw organisatie werken door rapporten te bekijken|[Beveiligingsdashboard](security-dashboard.md)<br/>[Beveiligingsrapporten voor e-mail](view-email-security-reports.md)<br/>[Rapporten voor Office 365 ATP](view-reports-for-atp.md)<br/>[Bedreigingsverkenner](threat-explorer.md)|
|Uw beleid voor bedreigingsbescherming periodiek herzien en herzien indien nodig|[Secure Score](../mtp/microsoft-secure-score.md)<br/>[Slimme rapporten en inzichten](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365-functies voor bedreigingsonderzoek en -reactie](keep-users-safe-with-office-365-ti.md)|
|Kijk voor nieuwe functies en service-updates|[Standaard- en gerichte releaseopties](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Berichtencentrum](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Microsoft 365-routekaart](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Servicebeschrijvingen](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
