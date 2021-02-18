---
title: Detecteer en herstel de Outlook-regels en aanvallen met aangepaste formulieren.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Meer informatie over het herkennen en herstellen van de Outlook-regels en aanvallen met aangepaste formulieren voor insinjecties in Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e22cfa97ae59fdd094c161cdaeff899dc1dd6507
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286391"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Outlook-regels en aangepaste formulieren-insinjecties detecteren en herstellen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Overzicht** Meer informatie over het herkennen en herstellen van de Outlook-regels en aangepaste Forms-insinjecties in Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Wat is de outlook-regels en aangepaste formuliereninjectie-aanval?

Nadat een aanvaller in uw tenancy een account heeft geschonden en binnenkomt, gaat u proberen een manier te vinden om binnen te blijven of terug te komen nadat deze zijn gevonden en verwijderd. Dit wordt een mechanisme voor persistentie genoemd. Twee manieren waarop ze dit kunnen doen, zijn door outlook-regels te misbruiken of aangepaste formulieren in te vullen in Outlook.
In beide gevallen wordt de regel of het formulier gesynchroniseerd van de cloudservice naar de desktopclient, dus bij volledige opmaak en opnieuw installeren van de clientsoftware wordt het insinjectiemechanisme niet weg. Dit komt omdat wanneer de Outlook-clientsoftware opnieuw verbinding maakt met het postvak in de cloud, de regels en formulieren opnieuw worden gedownload vanuit de cloud. Zodra de regels en formulieren zijn geïnstalleerd, gebruikt de aanvaller deze om externe of aangepaste code uit te voeren, meestal om malware op de lokale computer te installeren. Vervolgens wordt de malware inloggegevens opnieuw gestolen of worden andere activiteiten uitgevoerd.
Het goede nieuws is dat als uw clients worden gepatched naar de nieuwste versie, u niet kwetsbaar bent voor de bedreiging omdat de huidige Standaardinstellingen van de Outlook-client beide mechanismen blokkeren.

De aanvallen volgen meestal deze patronen:

**The Rules Exploit:**

1. De aanvaller stelen de gebruikersnaam en het wachtwoord van een van uw gebruikers.

2. De aanvaller meldt zich vervolgens aan bij het Exchange-postvak van die gebruiker. Het postvak kan zich in Exchange Online of on-premises in Exchange hebben.

3. De aanvaller maakt vervolgens een doorsturende regel in het postvak die wordt geactiveerd wanneer het postvak een e-mailbericht ontvangt dat voldoet aan de criteria van de regel. Het criterium van de regel en de inhoud van de trigger-e-mail zijn op elkaar afgestemd.

4. De aanvaller stuurt de trigger-e-mail naar de gebruiker die het postvak normaal gebruikt.

5. Wanneer het e-mailbericht wordt ontvangen, wordt de regel geactiveerd. De actie van de regel bestaat gewoonlijk uit het starten van een toepassing op een externe (WebDAV)-server.

6. Met de toepassing wordt malware, zoals [Powershell Empire,](https://www.powershellempire.com/)meestal lokaal op de computer van de gebruiker geïnstalleerd.

7. Met de malware kan de aanvaller de gebruikersnaam en het wachtwoord van de gebruiker of andere referenties van de lokale computer opnieuw stelen en andere schadelijke activiteiten uitvoeren.

**De Forms Exploit:**

1. De aanvaller stelen de gebruikersnaam en het wachtwoord van een van uw gebruikers.

2. De aanvaller kan zich vervolgens aanmelden bij dit Exchange-postvak. Het postvak kan zich in Exchange Online of on-premises in Exchange hebben.

3. De aanvaller maakt vervolgens een aangepaste e-mailformuliersjabloon en voegt deze in het postvak van de gebruiker in. Het aangepaste formulier wordt geactiveerd wanneer het postvak een e-mailbericht ontvangt dat vereist dat het aangepaste formulier door het postvak wordt geladen. Het aangepaste formulier en de opmaak van e-mail zijn op elkaar afgestemd.
4. De aanvaller stuurt de trigger-e-mail naar de gebruiker, die het postvak normaal gebruikt.

5. Wanneer het e-mailbericht wordt ontvangen, wordt het formulier geladen. Met het formulier wordt een toepassing op een externe (WebDAV)-server uitgevoerd.

6. Met de toepassing wordt malware, zoals [Powershell Empire,](https://www.powershellempire.com/)meestal lokaal op de computer van de gebruiker geïnstalleerd.

7. Met de malware kan de aanvaller de gebruikersnaam en het wachtwoord van de gebruiker of andere referenties van de lokale computer opnieuw stelen en andere schadelijke activiteiten uitvoeren.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Hoe kan een aanval met regels en een aangepaste formuliereninjectie eruit zien als Office 365?

Deze persistentiemechanismen zijn waarschijnlijk niet zichtbaar voor uw gebruikers en zijn in sommige gevallen zelfs onzichtbaar voor hen. In dit artikel wordt beschreven hoe u kunt zoeken naar een van de zeven tekens (Indicatoren van compromissen) die hieronder worden vermeld. Als u een van deze vindt, moet u herstelstappen nemen.

- Indicatoren van de regels zijn een compromis:

  - Regelactie is het starten van een toepassing.

  - Regel verwijst naar een EXE, ZIP of URL.

  - Zoek op de lokale computer naar een nieuw proces dat afkomstig is van de Outlook PID.

- Indicatoren van de aangepaste formulieren zijn een compromis:

  - Aangepast formulier dat is opgeslagen als hun eigen berichtklasse.

  - Berichtklasse bevat uitvoerbare code.

  - Wordt meestal opgeslagen in de Bibliotheek met persoonlijke formulieren of in postvak IN.

  - Formulier heeft de naam IPM. Opmerking. [aangepaste naam].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Stappen voor het vinden van tekens van deze aanval en het bevestigen ervan

U kunt een van deze twee methoden gebruiken om de aanval te bevestigen:

- De regels en formulieren voor elk postvak handmatig bekijken met behulp van de Outlook-client. Deze methode is grondig, maar u kunt de postvakgebruiker alleen controleren op een moment dat erg veel tijd in beslag kan nemen als u veel gebruikers moet controleren. Het kan ook leiden tot een schending van de computer van waardaan u de controle wilt uitvoeren.

- Gebruik het [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell-script om automatisch alle regels voor het doorsturen van e-mail en aangepaste formulieren voor alle gebruikers in uw tenancy tedumpen. Dit is de snelste en veiligste methode met de minste overhead.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>De regel-aanval bevestigen met de Outlook-client

1. Open de Outlook-client voor gebruikers als de gebruiker. De gebruiker heeft mogelijk uw hulp nodig bij het bestuderen van de regels voor het postvak.

2. Zie [E-mailberichten beheren met behulp van artikel](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) Regels voor de procedures voor het openen van de interface voor regels in Outlook.

3. Zoek naar regels die de gebruiker niet heeft gemaakt, of onverwachte regels of regels met verdachte namen.

4. Zoek in de regelbeschrijving naar regelacties die beginnen en worden gebruikt of die naar een . EXE, . ZIP-bestand of om een URL te starten.

5. Zoek naar nieuwe processen die de Outlook-proces-id gaan gebruiken. Raadpleeg De [proces-id zoeken.](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Stappen om de Forms-aanval te bevestigen met de Outlook-client

1. Open de Outlook-client van de gebruiker als gebruiker.

2. Volg de stappen in Het [tabblad Ontwikkelaars voor](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) de gebruikersversie van Outlook.

3. Open het nu zichtbare tabblad Ontwikkelaars in Outlook en klik op **een formulier ontwerpen.**

4. Selecteer het **Postvak IN** in de **lijst Zoeken in.** Zoek eventuele aangepaste formulieren. Aangepaste formulieren zijn zelden zo gebruikelijk dat u een beter uiterlijk kunt opvullen als u aangepaste formulieren hebt.

5. Onderzoek eventuele aangepaste formulieren, met name formulieren die zijn gemarkeerd als verborgen.

6. Open aangepaste formulieren en klik in de groep **Formulier** op **Code** weergeven om te zien wat er wordt uitgevoerd wanneer het formulier wordt geladen.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Stappen om de aanval van regels en formulieren met PowerShell te bevestigen

De eenvoudigste manier om een aanval van regels of aangepaste formulieren te controleren, is het [ uitvoeren ](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1)Get-AllTenantRulesAndForms.ps1PowerShell-script. Dit script maakt verbinding met elk postvak in uw tenant en alle regels en formulieren worden in twee CSV-bestanden opgeslagen.

#### <a name="pre-requisites"></a>Vereisten

U hebt een globale beheerdersrechten nodig om het script uit te voeren, omdat het script verbinding maakt met elk postvak in de tenancy om de regels en formulieren te lezen.

1. Meld u aan bij de computer vanaf waaruit u het script wilt uitvoeren met lokale beheerdersrechten.

2. Download of kopieer het Get-AllTenantRulesAndForms.ps1 script van GitHub naar een map waarin u het script wilt uitvoeren. Het script maakt twee bestanden met een datumstempel naar deze map, MailboxFormsExport-yyyy-mm-dd.csv en MailboxRulesExport-yyyy-mm-dd.csv.

3. Open een PowerShell-exemplaar als beheerder en open de map waarin u het script hebt opgeslagen.

4. Voer deze PowerShell-opdrachtregel als volgt uit `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>De uitvoer interpreteren

- **MailboxRulesExport-*yyyy-mm-dd*.csv:** Bekijk de regels (één per rij) voor actievoorwaarden die toepassingen of uitvoerbare bestanden bevatten:

  - **ActionType (kolom A)**: als u de waarde 'ID_ACTION_CUSTOM' ziet, is de regel waarschijnlijk schadelijk.

  - **IsVoltiallyMalicious (kolom D)**: Als deze waarde 'WAAR' is, is de regel waarschijnlijk schadelijk.

  - **ActionCommand (kolom G:** als hier een toepassing of een bestand met de extensie .exe, .zip of een vermelding die verwijst naar een URL wordt vermeld, dat daar niet zou moeten staan), is de regel waarschijnlijk schadelijk.

- **MailboxFormsExport-*yyyy-mm-dd*.csv:** Over het algemeen wordt het gebruik van aangepaste formulieren zeer zelden gebruikt. Als u een van deze werkmap vindt, opent u het postvak van die gebruiker en bekijkt u het formulier zelf. Als het in uw organisatie niet opzettelijk is gebeurd, is deze waarschijnlijk schadelijk.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>De outlook-regels- en forms-aanval stoppen en herstellen

Als u bewijs van een van deze aanvallen vindt, is herstel eenvoudig door de regel of het formulier uit het postvak te verwijderen. U kunt dit doen met de Outlook-client of met behulp van externe PowerShell om regels te verwijderen.

### <a name="using-outlook"></a>Outlook gebruiken

1. Identificeer alle apparaten die de gebruiker met Outlook heeft gebruikt. Ze moeten allemaal worden opgeschoond van mogelijke malware. Sta de gebruiker niet toe zich aan te melden en e-mail te gebruiken totdat alle apparaten zijn opgeschoond.

2. Volg de stappen in [Regel verwijderen voor](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) elk apparaat.

3. Als u niet zeker weet of er andere malware aanwezig is, kunt u alle software op het apparaat opmaken en opnieuw installeren. Voor mobiele apparaten kunt u de stappen van de fabrikanten volgen om het apparaat terug te zetten naar de fabrieksafbeelding.

4. Installeer de meest recente versies van Outlook. Onthoud dat in de huidige versie van Outlook beide typen van deze aanval standaard worden blokkeert.

5. Nadat alle offlinekopie's van het postvak zijn verwijderd, stelt u het wachtwoord van de gebruiker opnieuw in (gebruik een hoge kwaliteit) en volgt u de stappen [in](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) Meervoudige verificatie voor gebruikers instellen als MFA nog niet is ingeschakeld. Dit zorgt ervoor dat de referenties van de gebruiker niet op andere manier worden getoond (zoals phishing of het opnieuw gebruiken van een wachtwoord).

### <a name="using-powershell"></a>PowerShell gebruiken

Er zijn twee externe PowerShell-cmdlets die u kunt gebruiken om gevaarlijke regels te verwijderen of uit te schakelen. Volg de stappen.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Stappen voor postvakken die zich op een Exchange-server

1. Maak verbinding met de Exchange-server via externe PowerShell. Volg de stappen in [Verbinding maken met Exchange-servers via externe PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)

2. Als u één regel, meerdere regels of alle regels volledig uit een postvak wilt verwijderen, gebruikt u de cmdlet [Remove-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule)

3. Als u de regel en de inhoud ervan wilt behouden voor nader onderzoek, gebruikt u de cmdlet [Disable-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Stappen voor postvakken in Exchange Online

1. Volg de stappen in [Verbinding maken met Exchange Online via PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

2. Als u één regel, meerdere regels of alle regels volledig uit een postvak wilt verwijderen, gebruikt u de cmdlet [Regel](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) voor Het Postvak IN verwijderen.

3. Als u de regel en de inhoud ervan wilt behouden voor nader onderzoek, gebruikt u de cmdlet [Disable-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule)

## <a name="how-to-minimize-future-attacks"></a>Toekomstige aanvallen minimaliseren

### <a name="first-protect-your-accounts"></a>Eerst: uw accounts beveiligen

De regels en formulieren worden alleen gebruikt door een aanvaller nadat ze een van uw gebruikersaccounts hebben gestolen of geschonden. Uw eerste stap om te voorkomen dat deze misbruiken tegen uw organisatie worden gebruikt, is uw gebruikersaccounts op een andere manier te beveiligen. Sommige van de meest voorkomende manieren waarop accounts worden gekleineerd, zijn via phishing- of [wachtwoordaanvallen.](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)

De beste manier om uw gebruikersaccounts, en met name uw beheerdersaccounts, te beveiligen, is het instellen van meervoudige verificatie [voor gebruikers.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) U moet ook het volgende doen:

- Houd in de gaten hoe uw [gebruikersaccounts worden gebruikt](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports)en worden gebruikt. Het is mogelijk dat u de eerste inbreuk niet voorkomt, maar u verkort de duur en de invloed van de inbreuk door deze sneller te detecteren. U kunt dit beveiligingsbeleid voor [Office 365 Cloud-apps](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) gebruiken om uw accounts te controleren en u te waarschuwen voor ongebruikelijke activiteiten:

  - **Meerdere mislukte** aanmeldingspogingen: dit beleid profielen uw omgeving en triggers waarschuwingen wanneer gebruikers meerdere mislukte aanmeldingsactiviteiten uitvoeren in één sessie met betrekking tot de geleerde basislijn, die een poging tot inbreuk kan aangeven.

  - **Onmogelijk reizen:** dit beleid profielen uw omgeving en activeren waarschuwingen wanneer activiteiten van dezelfde gebruiker worden gedetecteerd op verschillende locaties binnen een periode die korter is dan de verwachte reistijd tussen de twee locaties. Dit kan aangeven dat een andere gebruiker dezelfde referenties gebruikt. Als u dit afwijkende gedrag detecteert, vereist dit een eerste leerperiode van zeven dagen waarin het activiteitspatroon van een nieuwe gebruiker wordt geleerd.

  - **Ongebruikelijke imitatieactiviteiten (door gebruiker:** dit beleid profielen uw omgeving en triggers wanneer gebruikers meerdere imitatieactiviteiten uitvoeren in een enkele sessie met betrekking tot de basislijn die is geleerd, die een poging tot inbreuk kan aangeven).

- Gebruik een hulpprogramma zoals [Office 365 Secure Score om](https://securescore.office.com/) configuraties en gedrag van accountbeveiliging te beheren.

### <a name="second-keep-your-outlook-clients-current"></a>Tweede: Houd uw Outlook-clients actueel

Volledig bijgewerkte en gepatchte versies van Outlook 2013 en 2016 schakelen de regel-/formulieractie 'Toepassing starten' standaard uit. Zo zorgt u ervoor dat, zelfs als een aanvaller het account schendt, de regels en formulieracties worden geblokkeerd. U kunt de meest recente updates en beveiligingspatches installeren door de stappen te volgen in [Office-updates installeren.](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)

Dit zijn de patchversies voor uw Outlook 2013- en 2016-clients:

- **Outlook 2016:** 16.0.4534.1001 of hoger.

- **Outlook 2013:** 15.0.4937.1000 of hoger.

Zie voor meer informatie over de afzonderlijke beveiligingspatches:

- [Beveiligingspatche voor Outlook 2016](https://support.microsoft.com/help/3191883)

- [Beveiligingspatche voor Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Derde: Uw Outlook-clients controleren

Houd er rekening mee dat een aanvaller, zelfs wanneer de patches en updates zijn geïnstalleerd, de lokale computerconfiguratie kan wijzigen om het gedrag 'Toepassing starten' opnieuw in te stellen. U kunt Geavanceerd [groepsbeleidsbeheer gebruiken om](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) lokaal machinebeleid op uw klanten te controleren en af te dwingen.

U kunt zien of 'Toepassing starten' opnieuw is ingeschakeld via een overschakeling in het register aan de hand van de informatie in Het weergeven van het systeemregister met behulp van [64 bitsversies](https://support.microsoft.com/help/305097)van Windows. Controleer deze subsleutels:

- **Outlook 2016:**`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013:**`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Zoek de belangrijkste EnableUnsafeClientMailRules. Als deze is ingesteld op 1, is de beveiligingspatche van Outlook overgeslagen en is de computer kwetsbaar voor de aanval van formulier/regels. Als de waarde 0 is, wordt de actie Toepassing starten uitgeschakeld. Als de bijgewerkte en gepatchte versie van Outlook is geïnstalleerd en deze registersleutel niet aanwezig is, is een systeem niet kwetsbaar voor deze aanvallen.

Klanten met on-premises Exchange-installaties kunnen oudere versies van Outlook blokkeren zonder patches. Meer informatie over dit proces vindt u in het artikel [Outlook-clientblokkering configureren.](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Microsoft 365 beveiligen als een cybersecurity pro

Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen. Gebruik de [Microsoft 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Microsoft 365-tenant te implementeren.

- Taken die in de eerste 30 dagen moeten worden uitgevoerd. Deze hebben direct effect en weinig invloed op uw gebruikers.

- Taken die binnen 90 dagen moeten worden uitgevoerd. Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.

- Na 90 dagen. Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.

## <a name="see-also"></a>Zie ook:

- [Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector biedt een gedetailleerd overzicht van de Outlook-regels.

- [MAPI over HTTP en Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) in de Sensepost-blog over Mailrule Pwnage bespreekt een hulpprogramma met de naam Ruler waarmee u postvakken kunt misbruiken via Outlook-regels.

- [Outlook-formulieren en -shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) in het Sensepost-blog over Forms Threat Vector.

- [Ruler Codebase](https://github.com/sensepost/ruler)

- [Liniaalindicatoren voor compromissen](https://github.com/sensepost/notruler/blob/master/iocs.md)
