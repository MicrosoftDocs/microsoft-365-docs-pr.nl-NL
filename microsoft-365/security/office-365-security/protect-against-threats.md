---
title: Bescherm u tegen bedreigingen in Microsoft Defender voor Office 365, Anti-malware, Anti-Phishing, Anti-spam, Safe-koppelingen, Safe-bijlagen, Automatische installatie van nuluur (ZAP), MDO-beveiligingsconfiguratie
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 06/22/2021
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
ms.openlocfilehash: 7e37b67dbed75e3283070ba94321fcb03979a5a6
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105390"
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
>
> Als u handmatige configuratie van de meeste beleidsregels in Defender voor Office 365 wilt overslaan, kunt u vooraf ingestelde beveiligingsbeleidsregels op het niveau Standaard of Strikt gebruiken. Zie Vooraf ingestelde beveiligingsbeleidsregels [in EOP en Microsoft Defender](preset-security-policies.md)voor Office 365.

## <a name="requirements"></a>Vereisten

### <a name="subscriptions"></a>Abonnementen

Bedreigingsbeveiligingsfuncties zijn opgenomen in *alle* Microsoft- of Office 365-abonnementen; Sommige abonnementen hebben echter geavanceerde functies. De onderstaande tabel bevat de beveiligingsfuncties in dit artikel samen met de minimale abonnementsvereisten.

> [!TIP]
> Buiten de aanwijzingen om auditing in  te Office 365 Exchange Online Protection(**EOP)** worden stappen uitgevoerd om anti-malware, anti-phishing en antispam in te voeren. Dit kan vreemd lijken in een Defender voor Office 365 artikel, totdat u eraan herinnert (**Defender voor** Office 365 ) EOP bevat en verder bouwt.

<br>

****

|Beveiligingstype|Abonnementsvereiste|
|---|---|
|Auditregistratie (voor rapportagedoeleinden)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Beveiliging tegen malware|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Bescherming tegen phishing|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Beveiliging tegen ongewenste e-mail|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Bescherming tegen schadelijke URL's en bestanden in e-mail en Office documenten (Safe Koppelingen en Safe bijlagen)|[Microsoft Defender voor Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Rollen en machtigingen

Als u Defender wilt configureren Office 365 beleidsregels, moet u een passende rol krijgen toegewezen. Bekijk de onderstaande tabel voor rollen die deze acties kunnen uitvoeren.

<br>

****

|Rol of rollengroep|Waar kunt u meer informatie?|
|---|---|
|globale beheerder|[Over Microsoft 365-beheerdersrollen](../../admin/add-users/about-admin-roles.md)|
|Beveiligingsadministrator|[Machtigingen voor beheerdersrollen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online Organisatiebeheer|[Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo)|
|

Zie Machtigingen in de Microsoft 365 Defender [portal voor meer informatie.](permissions-microsoft-365-security-center.md)

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>Auditlogregistratie inschakelen voor rapportage en onderzoek

- Begin de auditregistratie eerder. U moet controleren om aan te zijn **voor** een aantal van de volgende stappen. Auditregistratie is beschikbaar in abonnementen met [Exchange Online.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) Als u gegevens wilt weergeven in bedreigingsbeveiligingsrapporten, [e-mailbeveiligingsrapporten](view-email-security-reports.md)en [Verkenner,](threat-explorer.md)moet auditregistratie zijn *aan.* Zie Zoeken in auditlogboek in- [of uitschakelen voor meer informatie.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>Deel 1 - Bescherming tegen malware in EOP

Zie [EOP anti-malwarebeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)voor meer informatie over de aanbevolen instellingen voor anti-malware.

1. Open de **pagina Anti-malware** in de Microsoft 365 Defender portal op <https://security.microsoft.com/antimalwarev2> .

2. Selecteer op **de pagina Anti-malware** het beleid Met de naam **Standaard (Standaard)** door op de naam te klikken.

3. Klik in het flyout met beleidsdetails dat wordt geopend op **Beveiligingsinstellingen bewerken** en configureer de volgende instellingen:
   - **Sectie Beveiligingsinstellingen:**
     - **Het algemene bijlagefilter inschakelen:** Selecteren (inschakelen). Klik **op Bestandstypen aanpassen** om meer bestandstypen toe te voegen.
     - **Automatische zuivering van** nul uur inschakelen voor malware: controleer of deze instelling is geselecteerd. Zie [Zero-hour Auto Purge (ZAP)](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware)voor malware voor meer informatie over ZAP voor malware.
   - **Meldingssectie:** Controleer of geen van de instellingen voor meldingen is geselecteerd.

   Klik op **Opslaan** wanneer u gereed bent.

4. Klik in de flyout met beleidsdetails weer op **Sluiten**.

Zie Anti-malwarebeleid configureren in EOP voor gedetailleerde instructies voor het configureren van [anti-malwarebeleid.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>Deel 2 - Bescherming tegen phishing in EOP en Defender voor Office 365

[Anti-phishingbeveiliging](anti-phishing-protection.md) is beschikbaar in abonnementen met [EOP.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Geavanceerde anti-phishingbeveiliging is beschikbaar in [Defender voor Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

Zie [EOP anti-phishingbeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) en [Anti-phishingbeleidsinstellingen in Microsoft Defender](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)voor Office 365 voor meer informatie over de aanbevolen instellingen voor anti-phishingbeleid.

In de volgende procedure wordt beschreven hoe u het standaard anti-phishingbeleid configureert. Instellingen die alleen beschikbaar zijn in Defender voor Office 365 zijn duidelijk gemarkeerd.

1. Open de **pagina Anti-phishing** in de Microsoft 365 Defender portal op <https://security.microsoft.com/antiphishing> .

2. Selecteer op **de pagina Anti-phishing** het beleid met de naam **Office365 AntiPhish Default (Standaard)** door op de naam te klikken.

3. Configureer de volgende instellingen in de flyout beleidsdetails die worden weergegeven:
   - **Phishingdrempel & beveiligingssectie:** Klik op **Beveiligingsinstellingen bewerken** en configureer de volgende instellingen in het flyout dat wordt geopend:
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

   - **Sectie** Acties: Klik op **Acties bewerken** en configureer de volgende instellingen in het flyout dat wordt geopend:
     - **Sectie Berichtacties:** De volgende instellingen configureren:
       - **Als bericht wordt gedetecteerd als een nagebootsde gebruiker:** <sup>\*</sup> Selecteer Het bericht in quarantaine **plaatsen.**
       - **Als bericht wordt gedetecteerd als een nagebootsd domein:** <sup>\*</sup> Selecteer Het bericht in quarantaine **plaatsen.**
       - **Als postvakinformatie een** nagebootste gebruiker detecteert: Selecteer Bericht verplaatsen naar de mappen Ongewenste e-mail van de geadresseerden (Standaard) of Het bericht in quarantaine plaatsen <sup>\*</sup> (Strikt).  
       - **Als bericht wordt gedetecteerd als spoof:** Selecteer **Bericht verplaatsen** naar de mappen ongewenste e-mail van de geadresseerden (Standaard) of **Het** bericht in quarantaine plaatsen (Strikt).
     - **Veiligheidstips & de sectie** Indicatoren: De volgende instellingen configureren:
       - **Eerste contactpersoon veiligheidstip**: Selecteren (in- of uit).
       - **Gebruikers imiteren veiligheidstip** <sup>\*</sup> : Selecteren (in- of uit).
       - **Domein-imitatie veiligheidstip** <sup>\*</sup> : Selecteren (in- of uit).
       - **Ongebruikelijke tekens voor gebruikers imiteren veiligheidstip** <sup>\*</sup> : Selecteren (in- of uit).
       - **Show (?) for unauthenticated senders for spoof**: Select (turn on).
       - **Tag 'via' laten zien:** Selecteren (in- of uit).

     Klik op **Opslaan** wanneer u gereed bent.

   <sup>\*</sup>Deze instelling is alleen beschikbaar in Defender voor Office 365.

4. Klik **op Opslaan** en klik vervolgens op **Sluiten**

Zie [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md) en [Anti-phishingbeleid configureren in Microsoft Defender](configure-mdo-anti-phishing-policies.md)voor meer informatie over het configureren van anti-phishingbeleid Office 365.

## <a name="part-3---anti-spam-protection-in-eop"></a>Deel 3 - Bescherming tegen spam in EOP

Zie [EOP antispambeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)voor meer informatie over de aanbevolen instellingen voor antispam.

1. Open de **pagina Antispambeleid** in de Microsoft 365 Defender portal op <https://security.microsoft.com/antispam> .

2. Selecteer op **de pagina Antispambeleid** het beleid **antispambeleid (standaard) in** de lijst door op de naam te klikken.

3. Configureer de volgende instellingen in de flyout beleidsdetails die worden weergegeven:
   - **Bulk e-maildrempel & sectie spameigenschappen:** Klik op Drempelwaarde en eigenschappen **voor spam bewerken.** Configureer de volgende instellingen in het flyout dat wordt weergegeven:
     - **Drempelwaarde voor bulksgewijs** e-mail: Stel deze waarde in op 5 (Strikt) of 6 (standaard).
     - Laat andere instellingen op hun standaardwaarden staan (**Uit** of **Geen**).

     Klik op **Opslaan** wanneer u gereed bent.

   - **Sectie Acties:** Klik op **Acties bewerken.** Configureer de volgende instellingen in het flyout dat wordt weergegeven:
     - **Sectie Berichtacties:**
       - **Spam:** Controleer **of Bericht verplaatsen naar map Ongewenste e-mail** is geselecteerd (standaard) of selecteer **Quarantainebericht** (Strikt).
       - **Spam met hoog vertrouwen:** Selecteer **Quarantainebericht.**
       - **Phishing:** Selecteer **Quarantainebericht.**
       - **Phishing met hoge betrouwbaarheid:** Controleer **of Quarantaineberichten** is geselecteerd.
       - **Bulksgewijs:** **Controleer of Bericht verplaatsen naar map Ongewenste e-mail** is geselecteerd (standaard) of selecteer **Quarantainebericht** (Strikt).
     - **Spam in quarantaine bewaren voor deze dagen:** controleer de waarde **30** dagen.
     - **Tips voor spamveiligheid inschakelen:** controleer of deze instelling is geselecteerd (ingeschakeld).
     - **Zap (Zero Hour Auto Purge)** inschakelen: controleer of deze instelling is geselecteerd (ingeschakeld).
       - **Phishingberichten inschakelen:** controleer of deze instelling is geselecteerd (ingeschakeld). Zie [Zero-hour Auto Purge (ZAP)](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing)voor phishing voor meer informatie.
       - **Spamberichten inschakelen:** controleer of deze instelling is geselecteerd (ingeschakeld). Zie [Zero-hour Auto Purge (ZAP)](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam)voor spam voor meer informatie.
     - **Sectie Meldingen:**
       - Selecteer **Spammeldingen voor eindgebruikers inschakelen.**
         - **Verzend elke (dagen) spammeldingen** voor eindgebruikers: controleer de waarde **3** dagen.
         - **Taal:** Controleer de waarde **Standaard of** selecteer een taal.

     Klik op **Opslaan** wanneer u gereed bent.

   - Sectie Toegestane en geblokkeerde afzenders en domeinen: Controleer of bewerk uw toegestane afzenders en toegestane domeinen, zoals beschreven in Lijsten met geblokkeerde afzenders maken [in EOP](create-block-sender-lists-in-office-365.md) of Lijsten met veilige **afzenders** [maken in EOP.](create-safe-sender-lists-in-office-365.md)

     Klik op **Opslaan** wanneer u gereed bent.

4. Klik op **Sluiten** wanneer u gereed bent.

Zie Antispambeleid configureren in EOP voor gedetailleerde instructies voor het configureren van [antispambeleid.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Deel 4 - Bescherming tegen schadelijke URL's en bestanden (Safe Koppelingen en Safe bijlagen in Defender voor Office 365)

Time-of-click-beveiliging tegen schadelijke URL's en bestanden is beschikbaar in abonnementen met Microsoft Defender voor [Office 365.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) Het is ingesteld via het [Safe bijlagen en](safe-attachments.md) Safe [koppelingenbeleid.](safe-links.md)

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Safe Bijlagenbeleid in Microsoft Defender voor Office 365

Zie voor meer informatie over de aanbevolen instellingen Safe bijlagen. [Safe instellingen voor bijlagen](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

1. Open de **Safe bijlagen** in de Microsoft 365 Defender portal op <https://security.microsoft.com/safeattachmentv2> .

2. Klik op **Safe pagina Bijlagen** op **Algemene** instellingen en configureer vervolgens de volgende instellingen op het flyout dat wordt weergegeven:
   - **Schakel Defender in voor Office 365 voor SharePoint, OneDrive en Microsoft Teams:** Schakel deze instelling in ( ![ Schakel ](../../media/scc-toggle-on.png) In).

     > [!IMPORTANT]
     > Controleer voordat u Safe bijlagen inschakelen voor SharePoint, OneDrive en Microsoft Teams of auditregistratie is ingeschakeld **in uw organisatie.** Deze actie wordt meestal uitgevoerd door iemand die de rol Auditlogboeken heeft toegewezen in Exchange Online. Zie Zoeken in [auditlogboek in- of uitschakelen voor meer informatie.](../../compliance/turn-audit-log-search-on-or-off.md)

   - **Schakel Safe documenten in voor Office clients:** Schakel deze instelling in ( ![ Schakel ](../../media/scc-toggle-on.png) In). Houd er rekening mee dat deze functie alleen beschikbaar en zinvol is met Microsoft 365 E5 of Microsoft 365 E5 Security licenties.
   - **Toestaan dat personen door de** beveiligde weergave kunnen klikken, zelfs als Safe documenten het bestand als schadelijk hebben geïdentificeerd: Controleer of deze instelling is uitgeschakeld (Schakel de knop ![ ](../../media/scc-toggle-off.png) Uit).

   Wanneer u klaar bent, klikt u op **Opslaan**

3. Klik op Safe **pagina Bijlagen** op ![ Pictogram ](../../media/m365-cc-sc-create-icon.png) Maken.

4. Configureer **in de wizard Safe bijlagenbeleid** dat wordt geopend de volgende instellingen:
   - **Uw beleidspagina een naam** geven:
     - **Naam:** Voer iets unieks en beschrijvends in.
     - **Beschrijving:** Voer een optionele beschrijving in.
   - **Pagina Gebruikers en domeinen:** Omdat dit uw eerste beleid is en u waarschijnlijk de dekking wilt maximaliseren, kunt u overwegen uw geaccepteerde domeinen [in](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) te voeren in **het** vak Domeinen. Anders kunt u de vakken **Gebruikers** **en** Groepen gebruiken voor meer gedetailleerde besturing. U kunt uitzonderingen opgeven door **Deze gebruikers, groepen** en domeinen uitsluiten te selecteren en waarden in te geven.
   - **Instellingen** pagina:
     - **Safe Attachments unknown malware response**: Select **Block**.
     - **Bijlage omleiden met gedetecteerde bijlagen:** Omleiding **inschakelen:** Schakel deze instelling in (selecteer) en voer een e-mailadres in om gedetecteerde berichten te ontvangen.
     - De detectierespons Safe bijlagen toepassen als het scannen niet kan worden voltooid **(time-out** of fouten) : Controleer of deze instelling is geselecteerd.

5. Wanneer u klaar bent, klikt u op **Verzenden** en klikt u vervolgens op **Gereed.**

6. (Aanbevolen) Als globale beheerder of SharePoint Online-beheerder kunt u de cmdlet **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** uitvoeren met de parameter _DisallowInfectedFileDownload_ die is ingesteld `$true` op in SharePoint Online PowerShell.
   - `$true` blokkeert alle acties (behalve Verwijderen) voor gedetecteerde bestanden. Personen kunnen gedetecteerde bestanden niet openen, verplaatsen, kopiëren of delen.
   - `$false` blokkeert alle acties, behalve Verwijderen en Downloaden. Personen kunnen ervoor kiezen om het risico te accepteren en een gedetecteerd bestand te downloaden.

7. U kunt maximaal 30 minuten toestaan dat uw wijzigingen worden verspreid naar alle Microsoft 365 datacenters.

Zie de volgende onderwerpen voor gedetailleerde instructies Safe het configureren van bijlagebeleid en algemene instellingen voor Safe bijlagen:

- [Het beleid Safe bijlagen instellen in Microsoft Defender voor Office 365](set-up-safe-attachments-policies.md)
- [Veilige bijlagen uitschakelen voor SharePoint, OneDrive en Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)
- [Veilige documenten in Microsoft 365 E5](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Safe Beleidsregels voor koppelingen in Microsoft Defender voor Office 365

Zie voor meer informatie over de aanbevolen instellingen voor Safe Koppelingen [Safe Koppelingen.](recommended-settings-for-eop-and-office365.md#safe-links-settings)

1. Open de **pagina Safe koppelingen** in de Microsoft 365 Defender portal op <https://security.microsoft.com/safelinksv2> .

2. Klik op **Safe pagina Koppelingen** op **Algemene** instellingen en configureer vervolgens de volgende instellingen op het flyout dat wordt weergegeven:
   - **Instellingen die van toepassing zijn op inhoud in de** sectie Office 365 apps:
     - **Gebruik Safe Koppelingen in Office 365 apps:** Controleren of deze instelling is ingeschakeld ( ![ Schakelknop ](../../media/scc-toggle-on.png) in).
     - **Houd niet bij wanneer gebruikers op beveiligde koppelingen klikken in** Office 365 apps: Schakel deze instelling uit ( Schakel schakel ![ ](../../media/scc-toggle-off.png) uit).
     - **Laat gebruikers niet doorklikken naar de** oorspronkelijke URL in Office 365 apps: Controleren of deze instelling is ingeschakeld ( ![ Schakelknop ](../../media/scc-toggle-on.png) in).

   Wanneer u klaar bent, klikt u op **Opslaan**

3. Klik op Safe **pagina Koppelingen** op ![ Pictogram ](../../media/m365-cc-sc-create-icon.png) maken.

4. Configureer **de volgende instellingen Safe de** wizard Beleid maken Safe koppelingen die wordt geopend:
   - **Uw beleidspagina een naam** geven:
     - **Naam:** Voer iets unieks en beschrijvends in.
     - **Beschrijving:** Voer een optionele beschrijving in.
   - **Pagina Gebruikers en domeinen:** Omdat dit uw eerste beleid is en u waarschijnlijk de dekking wilt maximaliseren, kunt u overwegen uw geaccepteerde domeinen [in](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) te voeren in **het** vak Domeinen. Anders kunt u de vakken **Gebruikers** **en** Groepen gebruiken voor meer gedetailleerde besturing. U kunt uitzonderingen opgeven door **Deze gebruikers, groepen** en domeinen uitsluiten te selecteren en waarden in te geven.
   - **Pagina Beveiligingsinstellingen:**
     - **Selecteer de actie voor onbekende potentieel schadelijke URL's in berichten:** Schakel deze instelling **in.**
     - Selecteer de actie voor onbekende of potentieel schadelijke **URL's binnen** Microsoft Teams : Schakel deze instelling **in.** Vanaf maart 2020 is deze instelling beschikbaar in Preview en is alleen beschikbaar of functioneel voor leden van het Microsoft Teams Technology Adoption Program (TAP).
     - **Realtime URL-scan toepassen op verdachte koppelingen en koppelingen** die naar bestanden wijzen: Selecteer deze instelling (in- of uit).
       - **Wacht totdat URL-scannen is voltooid voordat het bericht wordt weergegeven:** Selecteer deze instelling (in- of uit).
     - **De Safe koppelingen toepassen op e-mailberichten die binnen** de organisatie zijn verzonden: Selecteer deze instelling (in- of uit).
     - **Gebruikersklikken niet bijhouden:** controleer of deze instelling niet is geselecteerd (uitgeschakeld).
     - **Laat gebruikers niet doorklikken naar de oorspronkelijke URL:** controleer of deze instelling is ingeschakeld (geselecteerd).
     - **De** huisstijl van de organisatie weergeven op meldings- en waarschuwingspagina's: Het selecteren van deze instelling (in- en uitschakelen) is pas zinvol nadat u de instructies hebt gevolgd in [Het Microsoft 365-thema](../../admin/setup/customize-your-organization-theme.md) aanpassen voor uw organisatie om uw bedrijfslogo te uploaden.
     - **De volgende URL's niet opnieuw schrijven:** we hebben geen specifieke aanbeveling voor deze instelling. Zie 'De volgende [URL's niet](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)opnieuw schrijven' in Safe Koppelingenbeleid voor meer informatie.
   - **Meldingspagina:**
     - **Hoe wilt u gebruikers op de hoogte stellen?** sectie: Desgewenst kunt u Aangepaste meldingstekst gebruiken selecteren **om** aangepaste meldingstekst in te voeren die u wilt gebruiken. U kunt ook **Gebruik Microsoft Translator voor automatische lokalisatie** om de aangepaste meldingstekst te vertalen naar de taal van de gebruiker. Anders laat u **De standaardmeldingstekst gebruiken** geselecteerd.

5. Wanneer u klaar bent, klikt u op **Verzenden** en klikt u vervolgens op **Gereed.**

Zie de volgende onderwerpen voor gedetailleerde instructies Safe koppelingenbeleid en algemene instellingen voor Safe koppelingen:

- [Beleidsregels Safe Koppelingen instellen in Microsoft Defender voor Office 365](set-up-safe-links-policies.md)
- [Algemene instellingen configureren voor Safe koppelingen in Microsoft Defender voor Office 365](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a>Nu waarschuwingen instellen voor gedetecteerde bestanden in SharePoint Online of OneDrive voor Bedrijven

Als u een melding wilt ontvangen wanneer een bestand in SharePoint Online of OneDrive voor Bedrijven is geïdentificeerd als schadelijk, kunt u een waarschuwing instellen zoals in deze sectie wordt beschreven.

1. Ga in Microsoft 365 Defender portal bij <https://security.microsoft.com> naar **E-mail & samenwerking** \> **Polices & rules** Alert \> **policy**.

2. Klik op **de pagina Waarschuwingsbeleid** op **Nieuw waarschuwingsbeleid.**

3. De **wizard Nieuw waarschuwingsbeleid** wordt geopend. Configureer **op de** pagina Naam de volgende instellingen:
   - **Naam:** Voer een unieke en beschrijvende naam in. U kunt bijvoorbeeld Schadelijke bestanden typen in bibliotheken.
   - **Beschrijving:** Voer een optionele beschrijving in.
   - **Ernst:** Selecteer **Laag,** **Gemiddeld** of **Hoog.**
   - **Categorie:** Selecteer **Bedreigingsbeheer.**

   Wanneer u klaar bent, klikt u op **Volgende**

4. Configureer **op de pagina Waarschuwingsinstellingen** maken de volgende instellingen:
   - **Waar wilt u op waarschuwen?** sectie: **Activiteit wordt** gedetecteerd malware in \> **bestand**.
   - **Hoe wilt u dat de waarschuwing wordt geactiveerd?** Controleer elke **keer dat een activiteit overeenkomt met de** regel is geselecteerd.

   Wanneer u klaar bent, klikt u op **Volgende**

5. Configureer op de pagina Uw **geadresseerden** instellen de volgende instellingen:
   - **E-mailmeldingen verzenden:** controleer of deze instelling is gesecteerd.
   - **E-mailontvangers:** Selecteer een of meer globale beheerders, beveiligingsbeheerders of beveiligingslezers die een melding moeten ontvangen wanneer een schadelijk bestand wordt gedetecteerd.
   - **Dagelijkse meldingslimiet:** Controleer **of er geen limiet** is geselecteerd.

   Wanneer u klaar bent, klikt u op **Volgende**

6. Controleer op **de pagina** Uw instellingen controleren uw instellingen, controleer **Ja,** schakel deze direct in en klik op **Voltooien**

Zie Waarschuwingsbeleid in de Microsoft 365-compliancecentrum voor [meer informatie over waarschuwingsbeleid.](../../compliance/alert-policies.md)

> [!NOTE]
> Wanneer u klaar bent met configureren, gebruikt u deze koppelingen om werkbelastingsonderzoeken te starten:
>
>- [Statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)
>- [Gebruik de Microsoft 365 Defender portal voor het beheren van in quarantaine geplaatste bestanden in Defender voor Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [Wat moet u doen als er een schadelijk bestand wordt gevonden in SharePoint Online, OneDrive of Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [In quarantaine geplaatste berichten en bestanden beheren als beheerder in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a>Taken na installatie en volgende stappen

Controleer na het configureren van de functies voor bedreigingsbeveiliging hoe deze functies werken. Controleer en wijzig uw beleid, zodat ze doen wat u nodig hebt. Let ook op nieuwe functies en service-updates die waarde kunnen toevoegen.

<br>

****

|Wat moet u doen?|Informatiebronnen|
|---|---|
|Bekijk hoe functies voor bedreigingsbeveiliging voor uw organisatie werken door rapporten te bekijken|[E-mailbeveiligingsrapporten](view-email-security-reports.md) <p> [Rapporten voor Microsoft Defender voor Office 365](view-reports-for-mdo.md) <p> [Bedreigingsverkenner](threat-explorer.md)|
|Controleer uw beleid voor bedreigingsbeveiliging regelmatig en wijzig deze zo nodig|[Secure Score](../defender/microsoft-secure-score.md) <p> [Microsoft 365 functies voor bedreigingsonderzoek en -antwoord](./office-365-ti.md)|
|Nieuwe functies en service-updates bekijken|[Standaard- en targeted releaseopties](../../admin/manage/release-options-in-office-365.md) <p> [Berichtencentrum](../../admin/manage/message-center.md) <p> [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Servicebeschrijvingen](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
