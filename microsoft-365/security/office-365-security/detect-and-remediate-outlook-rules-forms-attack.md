---
title: Detecteer en herstel de Outlook-regels en aangepaste formuliereninjecties.
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
description: Meer informatie over het herkennen en herstellen van de Outlook-regels en aangepaste formuliereninjecties in Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0846051b65b34ec26358f87bb4ca49302573e6e7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204393"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Outlook-regels en aangepaste formuliereninjecties detecteren en herstellen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Overzicht** Lees hoe u de Outlook-regels en aangepaste forms-injecties in Office 365 herkent en herstelt.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Wat is de outlook-regels en aangepaste formuliereninjectie-aanval?

Nadat een aanvaller toegang heeft tot uw organisatie, probeert hij of zij voet aan de grond te krijgen om binnen te blijven of weer binnen te komen nadat deze is gevonden. Deze activiteit wordt een *persistentiemechanisme genoemd.* Er zijn twee manieren waarop een aanvaller Outlook kan gebruiken om een persistentiemechanisme in te stellen:

- Door Gebruik te maken van Outlook-regels.
- Door aangepaste formulieren in Outlook te injecteren.

Het opnieuw installeren van Outlook of zelfs het geven van een nieuwe computer aan de getroffen persoon helpt niet. Wanneer de nieuwe installatie van Outlook verbinding maakt met het postvak, worden alle regels en formulieren gesynchroniseerd vanuit de cloud. De regels of formulieren zijn meestal ontworpen voor het uitvoeren van externe code en het installeren van malware op de lokale computer. De malware steelt referenties of voert andere illegale activiteiten uit.

Het goede nieuws is: als uw Outlook-clients worden gepatcht naar de nieuwste versie, bent u niet kwetsbaar voor de bedreiging, omdat de huidige Standaardinstellingen van Outlook-client beide mechanismen blokkeren.

De aanvallen volgen meestal deze patronen:

**Het gebruik van regels:**

1. De aanvaller steelt de referenties van een gebruiker.

2. De aanvaller meldt zich aan bij het Exchange-postvak van die gebruiker (Exchange Online of on-premises Exchange).

3. De aanvaller maakt een regel voor doorsturen van Postvak IN in het postvak. De doorsturende regel wordt geactiveerd wanneer het postvak een specifiek bericht ontvangt van de aanvaller die overeenkomt met de voorwaarden van de regel. De regelvoorwaarden en berichtindeling zijn op elkaar afgestemd.

4. De aanvaller stuurt de trigger-e-mail naar het gecompromitteerde postvak, dat nog steeds als normaal wordt gebruikt door de nietsvermoedende gebruiker.

5. Wanneer het postvak een bericht ontvangt dat overeenkomt met de voorwaarden van de regel, wordt de actie van de regel toegepast. De regelactie bestaat meestal uit het starten van een toepassing op een externe (WebDAV)-server.

6. Meestal installeert de toepassing malware op de computer van de gebruiker (bijvoorbeeld [PowerShell Empire).](https://www.powershellempire.com/)

7. Met de malware kan de aanvaller de gebruikersnaam en het wachtwoord van de gebruiker of andere referenties van de lokale computer stelen (of opnieuw stelen) en andere schadelijke activiteiten uitvoeren.

**De Forms Exploit:**

1. De aanvaller steelt de referenties van een gebruiker.

2. De aanvaller meldt zich aan bij het Exchange-postvak van die gebruiker (Exchange Online of on-premises Exchange).

3. De aanvaller voegt een aangepaste e-mailformuliersjabloon in het postvak van de gebruiker in. Het aangepaste formulier wordt geactiveerd wanneer het postvak een specifiek bericht ontvangt van de aanvaller, zodat het postvak het aangepaste formulier moet laden. Het aangepaste formulier en de berichtindeling zijn op elkaar afgestemd.

4. De aanvaller stuurt de trigger-e-mail naar het gecompromitteerde postvak, dat nog steeds als normaal wordt gebruikt door de nietsvermoedende gebruiker.

5. Wanneer het postvak het bericht ontvangt, wordt het vereiste formulier geladen in het postvak. Het formulier start een toepassing op een externe (WebDAV)-server.

6. Meestal installeert de toepassing malware op de computer van de gebruiker (bijvoorbeeld [PowerShell Empire).](https://www.powershellempire.com/)

7. Met de malware kan de aanvaller de gebruikersnaam en het wachtwoord van de gebruiker of andere referenties van de lokale computer stelen (of opnieuw stelen) en andere schadelijke activiteiten uitvoeren.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Hoe kan een aanval op regels en aangepaste formuliereninjectie eruit zien als Office 365?

Deze persistentiemechanismen zullen waarschijnlijk niet worden opgemerkt door uw gebruikers en zijn in sommige gevallen zelfs onzichtbaar voor hen. In dit artikel wordt beschreven hoe u kunt zoeken naar een van de zeven tekens (indicatoren van compromissen) die hieronder worden weergegeven. Als u een van deze gevonden hebt, moet u herstelstappen nemen.

- **Indicatoren van het compromis Regels:**
  - Regelactie is om een toepassing te starten.
  - Regel Verwijst naar een EXE, ZIP of URL.
  - Zoek op de lokale computer naar nieuwe processen die afkomstig zijn van de Outlook PID.

- **Indicatoren van de compromissen voor aangepaste formulieren:**
  - Aangepaste formulieren presenteren die zijn opgeslagen als hun eigen berichtenklasse.
  - Berichtklasse bevat uitvoerbare code.
  - Meestal worden schadelijke formulieren opgeslagen in persoonlijke formulierenbibliotheek of Postvak IN-mappen.
  - Formulier heeft de naam IPM. Opmerking. [aangepaste naam].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Stappen voor het vinden van tekenen van deze aanval en het bevestigen van deze aanval

U kunt een van de volgende methoden gebruiken om de aanval te bevestigen:

- Bekijk handmatig de regels en formulieren voor elk postvak met behulp van de Outlook-client. Deze methode is grondig, maar u kunt slechts één postvak tegelijk controleren. Deze methode kan erg tijdrovend zijn als u veel gebruikers hebt om te controleren en mogelijk ook de computer die u gebruikt, besmet.

- Gebruik het [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell-script om automatisch alle regels voor het doorsturen van e-mail en aangepaste formulieren te dumpen voor alle gebruikers in uw huurperiode. Dit is de snelste en veiligste methode met de minste hoeveelheid overhead.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>De aanval regels bevestigen met de Outlook-client

1. Open de Outlook-client voor gebruikers als gebruiker. De gebruiker kan uw hulp nodig hebben bij het onderzoeken van de regels in zijn of haar postvak.

2. Raadpleeg [E-mailberichten beheren met behulp van artikel](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) regels voor de procedures voor het openen van de interface regels in Outlook.

3. Zoek naar regels die de gebruiker niet heeft gemaakt of onverwachte regels of regels met verdachte namen.

4. Zoek in de beschrijving van de regel naar regelacties die beginnen en toepassen of verwijzen naar een . EXE, . ZIP-bestand of om een URL te starten.

5. Zoek naar nieuwe processen die de Outlook-proces-id gaan gebruiken. Raadpleeg [De proces-id zoeken.](/windows-hardware/drivers/debugger/finding-the-process-id)

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Stappen om de forms-aanval te bevestigen met behulp van de Outlook-client

1. Open de Outlook-client van de gebruiker als gebruiker.

2. Volg de stappen in Het [tabblad Ontwikkelaars voor](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) de versie van Outlook van de gebruiker.

3. Open het nu zichtbare ontwikkelaarstabblad in Outlook en klik **op Een formulier ontwerpen.**

4. Selecteer het **Postvak IN** in de **lijst Zoeken in.** Zoek naar aangepaste formulieren. Aangepaste formulieren zijn zeldzaam genoeg dat als u aangepaste formulieren hebt, het de moeite waard is om het te bekijken.

5. Onderzoek aangepaste formulieren, met name formulieren die zijn gemarkeerd als verborgen.

6. Open aangepaste formulieren en  klik in de groep Formulier op **Code weergeven** om te zien wat er wordt uitgevoerd wanneer het formulier wordt geladen.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Stappen om de aanval Regels en formulieren te bevestigen met PowerShell

De eenvoudigste manier om een aanval op regels of aangepaste formulieren te controleren, is door het powershell-script [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) uitvoeren. Dit script maakt verbinding met elk postvak in uw tenant en dumpt alle regels en formulieren in twee CSV-bestanden.

#### <a name="pre-requisites"></a>Vereisten

U moet globale beheerdersrechten hebben om het script uit te voeren, omdat het script verbinding maakt met elk postvak in de huurperiode om de regels en formulieren te lezen.

1. Meld u aan bij de computer waaruit u het script wilt uitvoeren met lokale beheerdersrechten.

2. Download of kopieer het Get-AllTenantRulesAndForms.ps1 script van GitHub naar een map waaruit u het wilt uitvoeren. Het script maakt twee bestanden met datumstempels in deze map, MailboxFormsExport-yyyy-mm-dd.csv en MailboxRulesExport-yyyy-mm-dd.csv.

3. Open een PowerShell-exemplaar als beheerder en open de map waarin u het script hebt opgeslagen.

4. Voer deze PowerShell-opdrachtregel als volgt `.\Get-AllTenantRulesAndForms.ps1` uit.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>De uitvoer interpreteren

- **PostvakRulesExport-*yyyy-mm-dd*.csv**: Bekijk de regels (één per rij) voor actievoorwaarden die toepassingen of uitvoerbare bestanden bevatten:

  - **ActionType (kolom A)**: Als u de waarde 'ID_ACTION_CUSTOM' ziet, is de regel waarschijnlijk schadelijk.

  - **IsPotentiallyMalicious (kolom D)**: Als deze waarde 'WAAR' is, is de regel waarschijnlijk schadelijk.

  - **ActionCommand (kolom G)**: Als deze kolom een toepassing of bestand bevat met .exe- of .zip-extensies of een onbekend item dat verwijst naar een URL, is de regel waarschijnlijk schadelijk.

- **MailboxFormsExport-*yyyy-mm-dd*.csv:** Over het algemeen is het gebruik van aangepaste formulieren zeldzaam. Als u deze in deze werkmap vindt, opent u het postvak van die gebruiker en bekijkt u het formulier zelf. Als uw organisatie dit niet opzettelijk heeft gedaan, is het waarschijnlijk schadelijk.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>De outlook-regels en -formulieren-aanval stoppen en herstellen

Als u enig bewijs van een van deze aanvallen vindt, is herstel eenvoudig, maar verwijdert u de regel of het formulier uit het postvak. U kunt dit doen met de Outlook-client of met behulp van externe PowerShell om regels te verwijderen.

### <a name="using-outlook"></a>Outlook gebruiken

1. Identificeer alle apparaten die de gebruiker met Outlook heeft gebruikt. Ze moeten allemaal worden verwijderd van mogelijke malware. Sta de gebruiker niet toe zich aan te melden en e-mail te gebruiken totdat alle apparaten zijn opgeschoond.

2. Volg de stappen in [Een regel verwijderen](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) voor elk apparaat.

3. Als u niet zeker weet of er andere malware aanwezig is, kunt u alle software op het apparaat opmaken en opnieuw installeren. Voor mobiele apparaten kunt u de stappen van fabrikanten volgen om het apparaat terug te zetten naar de fabrieksafbeelding.

4. Installeer de meest recente versies van Outlook. De huidige versie van Outlook blokkeert standaard beide typen van deze aanval.

5. Nadat alle offline exemplaren van het postvak zijn verwijderd, stelt u het wachtwoord van de gebruiker opnieuw in (gebruik een wachtwoord van hoge kwaliteit) en volgt u de stappen [in](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) Meervoudige verificatie instellen voor gebruikers als MFA nog niet is ingeschakeld. Dit zorgt ervoor dat de referenties van de gebruiker niet worden getoond via andere middelen (zoals phishing of wachtwoord opnieuw gebruiken).

### <a name="using-powershell"></a>PowerShell gebruiken

Er zijn twee externe PowerShell-cmdlets die u kunt gebruiken om gevaarlijke regels te verwijderen of uit te schakelen. Volg de stappen.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Stappen voor postvakken die zich op een Exchange-server

1. Maak verbinding met de Exchange-server met behulp van externe PowerShell. Volg de stappen in [Verbinding maken met Exchange-servers met behulp van externe PowerShell.](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)

2. Als u één regel, meerdere regels of alle regels volledig wilt verwijderen uit een postvak, gebruikt u de cmdlet [Remove-InBoxRule.](/powershell/module/exchange/Remove-InboxRule)

3. Als u de regel en de inhoud ervan wilt behouden voor verder onderzoek, gebruikt u de cmdlet [Disable-InBoxRule.](/powershell/module/exchange/disable-inboxrule)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Stappen voor postvakken in Exchange Online

1. Volg de stappen in [Verbinding maken met Exchange Online met PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Als u één regel, meerdere regels of alle regels uit een postvak volledig wilt verwijderen, gebruikt u de cmdlet Regel voor Postvak [IN](/powershell/module/exchange/Remove-InboxRule) verwijderen.

3. Als u de regel en de inhoud ervan wilt behouden voor verder onderzoek, gebruikt u de cmdlet [Disable-InBoxRule.](/powershell/module/exchange/disable-inboxrule)

## <a name="how-to-minimize-future-attacks"></a>Toekomstige aanvallen minimaliseren

### <a name="first-protect-your-accounts"></a>Ten eerste: uw accounts beveiligen

De exploits Regels en formulieren worden alleen gebruikt door een aanvaller nadat deze een van de accounts van uw gebruiker heeft gestolen of geschonden. De eerste stap om het gebruik van deze exploits tegen uw organisatie te voorkomen, is dus het agressief beveiligen van uw gebruikersaccounts. Enkele van de meest voorkomende manieren waarop accounts worden geschonden, zijn phishing- of [wachtwoordaanvallen.](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)

De beste manier om uw gebruikersaccounts, en met name uw beheerdersaccounts, te [beveiligen,](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)is door meervoudige verificatie in te stellen voor gebruikers. U moet ook het volgende doen:

- Houd in de gaten hoe uw [gebruikersaccounts worden gebruikt.](/azure/active-directory/active-directory-view-access-usage-reports) U kunt de eerste inbreuk niet voorkomen, maar u verkort de duur en het effect van de inbreuk door deze eerder te detecteren. U kunt deze beleidsregels voor [cloud-app-beveiliging van Office 365](/cloud-app-security/what-is-cloud-app-security) gebruiken om uw accounts te controleren en u te waarschuwen voor ongebruikelijke activiteiten:

  - **Meerdere mislukte** aanmeldingspogingen: dit beleid profileert uw omgeving en activeert waarschuwingen wanneer gebruikers meerdere mislukte aanmeldingsactiviteiten uitvoeren in één sessie met betrekking tot de geleerde basislijn, wat kan duiden op een poging tot inbreuk.

  - **Onmogelijk reizen:** dit beleid maakt een profiel van uw omgeving en activeert waarschuwingen wanneer activiteiten van dezelfde gebruiker worden gedetecteerd op verschillende locaties binnen een periode die korter is dan de verwachte reistijd tussen de twee locaties. Dit kan aangeven dat een andere gebruiker dezelfde referenties gebruikt. Voor het detecteren van dit afwijkende gedrag is een eerste leerperiode van zeven dagen nodig, waarin het activiteitspatroon van een nieuwe gebruiker wordt geleerd.

  - Ongebruikelijke imitatieactiviteit **(door gebruiker)**: Dit beleid profileert uw omgeving en activeert waarschuwingen wanneer gebruikers meerdere nagebootste activiteiten in één sessie uitvoeren met betrekking tot de basislijn die is geleerd, wat kan duiden op een poging tot inbreuk.

- Gebruik een hulpprogramma zoals [Office 365 Secure Score om](https://securescore.office.com/) accountbeveiligingsconfiguraties en -gedrag te beheren.

### <a name="second-keep-your-outlook-clients-current"></a>Ten tweede: Uw Outlook-clients actueel houden

Volledig bijgewerkte en gepatchte versies van Outlook 2013 en 2016 schakelen standaard de regel/formulieractie 'Toepassing starten' uit. Dit zorgt ervoor dat zelfs als een aanvaller inbreuk maakt op het account, de regels en formulieracties worden geblokkeerd. U kunt de meest recente updates en beveiligingspatches installeren door de stappen in [Office-updates installeren te volgen.](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)

Hier zijn de patchversies voor uw Outlook 2013- en 2016-clients:

- **Outlook 2016**: 16.0.4534.1001 of hoger.

- **Outlook 2013**: 15.0.4937.1000 of hoger.

Zie voor meer informatie over de afzonderlijke beveiligingspatches:

- [Beveiligingspatch van Outlook 2016](https://support.microsoft.com/help/3191883)

- [Beveiligingspatch van Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Derde: Uw Outlook-clients controleren

Houd er rekening mee dat zelfs wanneer de patches en updates zijn geïnstalleerd, een aanvaller de lokale computerconfiguratie kan wijzigen om het gedrag van de 'Starttoepassing' opnieuw in te stellen. U kunt Geavanceerd [groepsbeleidsbeheer gebruiken om](/microsoft-desktop-optimization-pack/agpm/) lokaal machinebeleid op uw clients te controleren en af te dwingen.

U kunt zien of 'Toepassing starten' opnieuw is ingeschakeld via een overschrijven in het register met behulp van de informatie in Het systeemregister weergeven met behulp van [64-bits](https://support.microsoft.com/help/305097)versies van Windows. Controleer deze subsleutels:

- **Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Zoek naar de sleutel EnableUnsafeClientMailRules. Als deze is ingesteld op 1, is de beveiligingspatch van Outlook overgenomen en is de computer kwetsbaar voor de aanval Formulier/regels. Als de waarde 0 is, wordt de actie Toepassing starten uitgeschakeld. Als de bijgewerkte en gepatchte versie van Outlook is geïnstalleerd en deze registersleutel niet aanwezig is, is een systeem niet kwetsbaar voor deze aanvallen.

Klanten met on-premises Exchange-installaties moeten overwegen oudere versies van Outlook te blokkeren zonder patches. Meer informatie over dit proces vindt u in het artikel [Outlook-client blokkeren configureren.](/exchange/configure-outlook-client-blocking-exchange-2013-help)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Microsoft 365 beveiligen als een cybersecurity pro

Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen. Gebruik de [Microsoft 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Microsoft 365-tenant te implementeren.

- Taken die in de eerste 30 dagen moeten worden uitgevoerd. Deze hebben direct effect en hebben weinig invloed op uw gebruikers.

- Taken die binnen 90 dagen moeten worden uitgevoerd. Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.

- Na 90 dagen. Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.

## <a name="see-also"></a>Zie ook:

- [Kwaadaardige Outlook-regels](https://silentbreaksecurity.com/malicious-outlook-rules/) door SilentBreak Security Post over Rules Vector biedt een gedetailleerde beoordeling van de manier waarop de Outlook-regels.

- [MAPI via HTTP en Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) in de Sensepost-blog over Mailrule Pwnage bespreekt een hulpmiddel genaamd Liniaal waarmee u postvakken kunt gebruiken via Outlook-regels.

- [Outlook-formulieren en -shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) op de Sensepost-blog over Forms Threat Vector.

- [LiniaalCodebase](https://github.com/sensepost/ruler)

- [Liniaalindicatoren van compromissen](https://github.com/sensepost/notruler/blob/master/iocs.md)