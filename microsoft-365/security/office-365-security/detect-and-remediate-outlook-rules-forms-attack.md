---
title: Opsporen en herstellen van de Outlook-regels en aangepaste Forms-injectie aanvallen.
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Leer hoe u Outlook-regels en aangepaste Forms-injectie aanvallen in Office 365 herkent en verhelpt
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7d879d34a925354084e08d82f5e1724725c18825
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203069"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Outlook-regels en aangepaste Forms-injecties detecteren en herstellen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Overzicht** Leer hoe u Outlook-regels en aangepaste Forms-injectie aanvallen in Office 365 herkent en verhelpt.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Wat zijn de Outlook-regels en aangepaste Forms-injectie aanval?

Wanneer een hacker een account heeft geschonden in uw pacht en erin komt, is er een manier om op de hoogte te blijven van en tot stand te brengen, zodat u kunt teruggaan, zodat u kunt teruggaan naar de weergave. Dit noemen we een Persistence mechanisme opzetten. U kunt dit op twee manieren doen door gebruik te maken van Outlook-regels of door aangepaste formulieren in Outlook te injecteren.
In beide gevallen wordt de regel of het formulier gesynchroniseerd van de cloudservice naar de desktopclient, zodat het inspuit mechanisme niet wordt verholpen door een volledige indeling te krijgen en opnieuw te installeren. Dit komt omdat wanneer de Outlook-clientsoftware opnieuw verbinding maakt met het postvak in de Cloud, worden de regels en formulieren van de Cloud opnieuw gedownload. Wanneer de regels en formulieren zijn geplaatst, wordt deze door de aanvaller gebruikt voor het uitvoeren van externe of aangepaste code, doorgaans om malware op de lokale computer te installeren. De malware onthoudt vervolgens referenties of andere ongeoorloofde activiteiten.
Het goede nieuws dat u doet, als u de clients bijwerkt naar de nieuwste versie, kunt u niet alleen de bedreiging van de huidige instellingen voor de Outlook-client blokkeren.

De aanvallen volgen meestal de volgende patronen:

**De regels die u exploiteert**:

1. De hacker ontneemt de gebruikersnaam en het wachtwoord van een van uw gebruikers.

2. De aanvaller meldt zich aan bij het Exchange-postvak van die gebruiker. Het postvak kan zich bevinden in Exchange Online of in Exchange on-premises.

3. De aanvaller maakt vervolgens een doorstuurregel in het postvak dat wordt geactiveerd wanneer het postvak een e-mail ontvangt die voldoet aan de criteria van de regel. De criteria van de regel en de inhoud van het trigger-e-mailbericht zijn voor elkaar op maat gemaakt.

4. De aanvaller verzendt de e-mail van de trigger naar de gebruiker die zijn of haar Postvak normaal gebruikt.

5. Wanneer de e-mail wordt ontvangen, wordt de regel geactiveerd. De actie van de regel is meestal het starten van een toepassing op een externe (WebDAV)-server.

6. De toepassing installeert doorgaans malware, zoals [PowerShell Empire](https://www.powershellempire.com/), lokaal op de computer van de gebruiker.

7. De malware laat de kwaadwillende persoon de gebruikersnaam en het wachtwoord van de gebruiker of andere referenties van de lokale computer opnieuw stelen en andere schadelijke activiteiten uitvoeren.

**Het gebruik van formulieren**:

1. De hacker ontneemt de gebruikersnaam en het wachtwoord van een van uw gebruikers.

2. De aanvaller meldt zich aan bij het postvak van de gebruikers in het Exchange-postvak. Het postvak kan zich bevinden in Exchange Online of in Exchange on-premises.

3. De aanvaller maakt vervolgens een aangepaste e-mail formuliersjabloon en voegt deze in het postvak van de gebruiker in. Het aangepaste formulier wordt geactiveerd wanneer het postvak een e-mailbericht ontvangt dat het postvak nodig heeft om het aangepaste formulier te laden. Het aangepaste formulier en de indeling van e-mailberichten worden voor elkaar gemaakt.
4. De aanvaller verzendt de e-mail van de trigger naar de gebruiker, die hun postvak normaal gebruikt.

5. Wanneer het e-mailbericht wordt ontvangen, wordt het formulier geladen. Het formulier start een toepassing op een externe (WebDAV)-server.

6. De toepassing installeert doorgaans malware, zoals [PowerShell Empire](https://www.powershellempire.com/), lokaal op de computer van de gebruiker.

7. De malware laat de kwaadwillende persoon de gebruikersnaam en het wachtwoord van de gebruiker of andere referenties van de lokale computer opnieuw stelen en andere schadelijke activiteiten uitvoeren.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Welke regels en aangepaste Forms-injectie aanval lijken op Office 365?

Deze permanente mechanismen zijn niet zichtbaar voor uw gebruikers en kunnen in sommige gevallen zelfs onzichtbaar zijn. In dit artikel wordt uitgelegd hoe u in de onderstaande lijst kunt zoeken naar alle zeven tekenen (niet aanwezig). Als u een van deze bevindt, moet u stappen uitvoeren om herstel stappen uit te voeren.

- Indicatoren voor de regels komen niet in orde:

  - De regelactie is om een toepassing te starten.

  - Regel verwijst naar een EXE, ZIP of URL.

  - Op de lokale computer gaat u naar nieuw proces dat is gemaakt op basis van de Outlook-PID.

- Indicatoren voor het aanbrengen van aangepaste formulieren:

  - Een aangepast formulier dat is opgeslagen als hun eigen berichtklasse.

  - Berichtenklasse bevat uitvoerbare code.

  - Meestal opgeslagen in mappen met persoonlijke formulierbibliotheek of postvak in.

  - Formulier heeft de naam IPM. Ziet. [aangepaste naam].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Stappen voor het vinden van tekenen van deze aanval en het bevestigen

U kunt een van de volgende twee methoden gebruiken om de aanval te bevestigen:

- Onderzoek de regels en formulieren voor elk postvak handmatig met behulp van de Outlook-client. Deze methode is uitgebreid, maar u kunt de gebruiker van het postvak op een bepaald moment gebruiken, zodat u veel tijd hebt om te controleren of u veel gebruikers moet controleren. Het kan ook leiden tot een schending van de computer waarop u de controle uitvoert.

- Met de [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell-script worden alle regels voor het doorsturen van e-mail en aangepaste formulieren automatisch gedumpt voor alle gebruikers in uw pacht. Dit is de snelste en de veiligste methode met het minste Overheadbedrag.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>De regels voor een aanval via de Outlook-client bevestigen

1. Open de Outlook-clientgebruikers als de gebruiker. De gebruiker moet mogelijk uw hulp nodig hebben bij het onderzoeken van de regels in hun postvak.

2. Zie [e-mailberichten beheren met behulp](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) van het artikelregels voor de procedures voor het openen van de regels interface in Outlook.

3. Zoek naar regels die de gebruiker niet heeft gemaakt of onverwachte regels of regels met verdachte namen.

4. Let op de regelbeschrijving voor de regelacties die beginnen en Application of waarnaar wordt verwezen. EXE,. ZIP-bestand of om een URL te starten.

5. Zoek naar nieuwe processen die aan de slag gaan met de Outlook-proces-ID. Zie [de proces-id zoeken](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Stappen voor het controleren van de Forms-aanval met behulp van de Outlook-client

1. Open de Outlook-client voor de gebruiker als de gebruiker.

2. Volg de stappen in [het tabblad Ontwikkelaars](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) voor de gebruikersversie van Outlook weergeven.

3. Open het tabblad ontwikkelaars nu in Outlook en klik op **een formulier ontwerpen**.

4. Selecteer het **Postvak in** in de lijst **Zoeken in** . Zoek naar aangepaste formulieren. Aangepaste formulieren lijken voldoende te zijn, als u helemaal een aangepast formulier hebt, is dit een betere uitstraling.

5. Onderzoek aangepaste formulieren, met name die zijn gemarkeerd als verborgen.

6. Open eventuele aangepaste formulieren en klik in de groep **formulier** op **code weergeven** om te zien wat er wordt uitgevoerd wanneer het formulier wordt geladen.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Stappen voor het controleren van de regels en formulieren aanval met behulp van PowerShell

De eenvoudigste manier om een aanval met een regel te controleren, is door het [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell-script uit te voeren. Dit script maakt verbinding met elk postvak in uw Tenant en verdeelt alle regels en formulieren in twee. CSV-bestanden.

#### <a name="pre-requisites"></a>Vereisten

U moet een globale beheerdersrechten hebben om het script uit te voeren omdat het script verbinding maakt met elk postvak in de pacht om de regels en formulieren te lezen.

1. Meld u aan bij de computer waarop u het script wilt uitvoeren met lokale beheerdersrechten.

2. Download of kopieer het Get-AllTenantRulesAndForms.ps1 script van GitHub naar een map waaruit u het wilt uitvoeren. Met het script kunt u twee datumstempel bestanden maken in deze map, MailboxFormsExport-yyyy-mm-dd.csv en MailboxRulesExport-yyyy-mm-dd.csv.

3. Open een PowerShell-exemplaar als beheerder en open de map waarin u het script hebt opgeslagen.

4. Voer de volgende opdracht uit op de PowerShell-opdrachtregel `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>De uitvoer interpreteren

- **MailboxRulesExport-*jjjj-mm-dd*. CSV**: Bekijk de regels (één per rij) voor actie voorwaarden die toepassingen of uitvoerbare bestanden bevatten:

  - **ActionType (kolom A)**: als de waarde ' ID_ACTION_CUSTOM ' wordt weergegeven, is de regel waarschijnlijk schadelijk.

  - **IsPotentiallyMalicious (kolom D)**: als deze waarde "True" is, is de regel waarschijnlijk schadelijk.

  - **ActionCommand (kolom G)**: als dit een toepassing of een bestand met een exe-, zip-extensie is of een vermelding die verwijst naar een URL, dan is de regel waarschijnlijk schadelijk.

- **MailboxFormsExport-*jjjj-mm-dd*. CSV**: in het algemeen is het gebruik van aangepaste formulieren zeer zeldzaam. Als u een van deze werkmappen vindt, opent u het postvak van de gebruiker en bekijkt u het formulier zelf. Als het niet is gelukt om het te doen, is de organisatie waarschijnlijk schadelijk.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Het aanvals formulier voor regels en formulieren stoppen en herstellen

Als u enig bewijs vindt van een van deze aanvallen, is herstel eenvoudig en hoeft u alleen maar de regel of het formulier uit het postvak te verwijderen. U kunt dit doen met de Outlook-client of met behulp van externe PowerShell om regels te verwijderen.

### <a name="using-outlook"></a>Outlook gebruiken

1. Identificeer alle apparaten die de gebruiker heeft gebruikt met Outlook. Ze moeten allemaal de mogelijke malware wissen. Gebruikers kunnen zich niet aanmelden bij en e-mail gebruiken totdat alle apparaten zijn opgeschoond.

2. Volg de stappen in [een regel verwijderen](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) voor elk apparaat.

3. Als u niet zeker weet wat de aanwezigheid van andere malware is, kunt u de software op het apparaat formatteren en opnieuw installeren. Voor mobiele apparaten kunt u de stappen van de fabrikant volgen om het apparaat opnieuw in te stellen voor de fabrieks afbeelding.

4. Installeer de meest recente versies van Outlook. Houd er rekening mee dat de huidige versie van Outlook standaard beide soorten aanval blokkeert.

5. Wanneer alle offlinekopieën van het postvak zijn verwijderd, moet u het wachtwoord van de gebruiker opnieuw instellen (gebruik een hoge kwaliteit) en voert u de stappen uit [voor meervoudige verificatie instellen voor gebruikers](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) als MFA nog niet is ingeschakeld. Hierdoor wordt voorkomen dat de referenties van de gebruiker op andere wijze worden weergegeven, zoals phishing of wachtwoord opnieuw gebruiken.

### <a name="using-powershell"></a>PowerShell gebruiken

U kunt twee externe PowerShell-cmdlets gebruiken om gevaarlijke regels te verwijderen of uit te schakelen. Voer gewoon de stappen uit.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Stappen voor postvakken op een Exchange-Server

1. Maak verbinding met de Exchange-server via Remote PowerShell. Volg de stappen in [verbinding maken met Exchange-servers via externe PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell).

2. Als u één regel, meerdere regels of alle regels van een postvak volledig wilt verwijderen, gebruikt u de cmdlet [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) .

3. Als u de regel en de inhoud ervan wilt bewaren voor verder onderzoek, gebruikt u de cmdlet [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) .

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Stappen voor postvakken in Exchange Online

1. Volg de stappen in [verbinding maken met Exchange Online via PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

2. Als u één regel, meerdere regels of alle regels van een postvak volledig wilt verwijderen, gebruikt u de cmdlet [regel voor het postvak in](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) .

3. Als u de regel en de inhoud ervan wilt bewaren voor verder onderzoek, gebruikt u de cmdlet [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) .

## <a name="how-to-minimize-future-attacks"></a>Toekomstige aanvallen minimaliseren

### <a name="first-protect-your-accounts"></a>First: uw accounts beschermen

De exploits van regels en formulieren worden alleen door een aanvaller gebruikt nadat ze een van de accounts van uw gebruikers hebben gestolen of geschendd. Dus als u wilt voorkomen dat u dit exploiteert tegen uw organisatie, moet u uw gebruikersaccounts eerst beschermen. Een aantal van de meest voorkomende manieren om accounts te schenden, loopt via phishing of het [spuiten van wachtwoorden](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) .

De beste manier om uw gebruikersaccounts te beschermen en met name uw beheerdersaccounts is door [Meervoudige verificatie in te stellen voor gebruikers](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication). U moet ook het volgende doen:

- Controleer hoe uw gebruikersaccounts worden [geopend en gebruikt](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports). U kunt de eerste schending niet voorkomen, maar u zult de duur en de impact van de schending verkorten door het sneller te ontdekken. U kunt deze [beveiligings beleidsregels voor Office 365 Cloud app](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) gebruiken om de accounts en waarschuwingen voor ongebruikelijke activiteiten te controleren:

  - **Meerdere mislukte aanmeldpogingen**: dit beleid maakt deel uit van de omgeving en u ontvangt waarschuwingen wanneer gebruikers meerdere mislukte aanmeld activiteiten uitvoeren in één sessie met betrekking tot de uitgelichte basislijn, wat kan leiden tot schending van de geleerde basislijn.

  - Niet **reis**: met dit beleid worden uw omgevings profielen en waarschuwingen geactiveerd wanneer activiteiten worden gedetecteerd van dezelfde gebruiker op verschillende locaties binnen een bepaalde periode die korter is dan de verwachte reistijd tussen de twee locaties. Dit kan betekenen dat een andere gebruiker dezelfde referenties gebruikt. Het detecteren van dit afwijkend gedrag vergt een eerste leer periode van zeven dagen waarover de activiteiten van een nieuwe gebruiker worden gemaakt.

  - **Ongebruikelijk geïmiteerde activiteit (door gebruiker)**: dit beleid is van toepassing op de omgeving en u ontvangt waarschuwingen wanneer gebruikers meerdere geïmiteerde activiteiten uitvoeren in één sessie met betrekking tot de basislijn die kan worden geprobeerd.

- Maak gebruik van een hulpmiddel zoals een [Secure Score van Office 365](https://securescore.office.com/) voor het beheren van beveiligingsconfiguraties en-gedrag van uw account.

### <a name="second-keep-your-outlook-clients-current"></a>Tweede: de Outlook-clients actueel houden

Volledig gewijzigde en verstuurde versies van Outlook 2013 en 2016 Schakel de regel ' toepassing ' uit en schakel de actie ' toepassing starten ' uit. Dit zorgt ervoor dat, zelfs als een aanvaller het account schendt, de acties regel en formulier worden geblokkeerd. U kunt de meest recente updates en beveiligingspatches installeren door de stappen te volgen in [Office-updates installeren](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5).

Dit zijn de patch versies voor uw clients met Outlook 2013 en 2016:

- **Outlook 2016**: 16.0.4534.1001 of hoger.

- **Outlook 2013**: 15.0.4937.1000 of hoger.

Zie voor meer informatie over de afzonderlijke beveiligingspatches:

- [Beveiligings patch voor Outlook 2016](https://support.microsoft.com/help/3191883)

- [Beveiligings patch voor Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Derde: uw Outlook-clients controleren

Ook als de patches en updates zijn geïnstalleerd, is de mogelijkheid van een aanvaller de configuratie van lokale machines te wijzigen om het gedrag van de toepassing starten weer in te schakelen. U kunt [Geavanceerd Groepsbeleidsbeheer](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) gebruiken voor het bewaken en afdwingen van beleid voor lokale computer op uw klanten.

U kunt zien of ' Start programma ' opnieuw is ingeschakeld via een overschrijving in het register met behulp van de informatie in het [weergeven van het systeemregister via 64-bits versies van Windows](https://support.microsoft.com/help/305097). Controleer de volgende subsleutels:

- **Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Zoek naar de sleutel EnableUnsafeClientMailRules. Als dat het geval is en is ingesteld op 1, is de beveiligingspatch voor Outlook overschreven en is de computer kwetsbaar voor het aanval formulier/regels. Als de waarde 0 is, is de actie toepassing starten uitgeschakeld. Als de bijgewerkte versie van Outlook is geïnstalleerd en deze registersleutel niet aanwezig is, is een systeem niet kwetsbaar voor deze aanvallen.

Voor klanten met on-premises Exchange-installaties moet u wellicht oudere versies van Outlook blokkeren waarop geen patches beschikbaar zijn. Meer informatie over dit proces vindt u in het artikel [Outlook-client blokkering configureren](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Microsoft 365 beveiligen als een cybersecurity pro

Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen. Gebruik de [Microsoft 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Microsoft 365-tenant te implementeren.

- Taken die in de eerste 30 dagen moeten worden uitgevoerd. Deze hebben direct effect en weinig invloed op uw gebruikers.

- Taken die binnen 90 dagen moeten worden uitgevoerd. Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.

- Na 90 dagen. Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.

## <a name="see-also"></a>Zie ook:

- [Kwaadwillende Outlook-regels](https://silentbreaksecurity.com/malicious-outlook-rules/) door SilentBreak beveiligingsbericht over regels vector bieden een uitgebreide controle over de manier waarop de Outlook-regels worden gebruikt.

- [MAPI via HTTP-en mail regel Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) in de Sensepost-blog over de mail regel Pwnage bespreekt een hulpmiddel genaamd liniaal waarmee u postvakken kunt gebruiken via Outlook-regels.

- [Outlook-formulieren en-shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) in de Sensepost-blog over Forms Threat vector.

- [Codebase voor liniaal](https://github.com/sensepost/ruler)

- [Liniaal indicatoren van compromissen](https://github.com/sensepost/notruler/blob/master/iocs.md)
