---
title: Detecteren en herstellen van de Outlook-regels en aangepaste formulieren injecties aanvallen.
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
description: Meer informatie over het herkennen en herstellen van outlook-regels en aangepaste aanvallen op het uitvoeren van formulieren in Office 365
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e18635b9b9d090dbc2808b5b8142b59ec1f29c6e
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224587"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a>Outlook-regels en injecties met aangepaste formulieren detecteren en herstellen

**Overzicht** Meer informatie over het herkennen en herstellen van de Outlook-regels en aangepaste formuliereninjecties in Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Wat is de injectieaanval met Outlook-regels en aangepaste formulieren?

Nadat een aanvaller een account in uw huurovereenkomst heeft geschonden en binnenkomt, zullen er proberen een manier te vinden om binnen te blijven of een manier om weer binnen te komen nadat ze zijn ontdekt en verwijderd. Dit wordt het opzetten van een persistentiemechanisme genoemd. Twee manieren waarop ze dit kunnen doen zijn door Outlook-regels te misbruiken of door aangepaste formulieren in Outlook te injecteren.
In beide gevallen wordt de regel of het formulier gesynchroniseerd van de cloudservice naar de desktopclient, zodat een volledig formaat en opnieuw installeren van de clientsoftware het injectiemechanisme niet elimineert. Dit komt omdat wanneer de Outlook-clientsoftware opnieuw verbinding maakt met het postvak in de cloud, de regels en formulieren opnieuw wordt gedownload uit de cloud. Zodra de regels en formulieren zijn op zijn plaats, de aanvaller gebruikt ze uit te voeren op afstand of aangepaste code, meestal om malware te installeren op de lokale machine. De malware vervolgens opnieuw steelt geloofsbrieven of voert andere illegale activiteiten.
Het goede nieuws hier is dat als u uw klanten gepatcht naar de nieuwste versie, bent u niet kwetsbaar voor de dreiging als de huidige Outlook client standaardinstellingen blokkeren beide mechanismen.

De aanvallen volgen meestal deze patronen:

**De regels exploiteren**:

1. De aanvaller steelt de gebruikersnaam en het wachtwoord van een van uw gebruikers.

2. De aanvaller meldt zich vervolgens aan bij dat exchange-postvak van gebruikers. De mailbox kan online in Exchange of in Exchange on-premises zijn.

3. De aanvaller maakt vervolgens een doorstuurregel in het postvak die wordt geactiveerd wanneer het postvak een e-mail ontvangt die overeenkomt met de criteria van de regel. De regels van de regel en de inhoud van de trigger e-mail zijn op maat gemaakt voor elkaar.

4. De aanvaller stuurt de triggere-mail naar de gebruiker die zijn postvak normaal gebruikt.

5. Wanneer de e-mail wordt ontvangen, wordt de regel geactiveerd. De actie van de regel is meestal om een toepassing te starten op een externe (WebDAV) server.

6. De applicatie installeert meestal malware, zoals [Powershell Empire](https://www.powershellempire.com/), lokaal op de machine van de gebruiker.

7. De malware kan de aanvaller opnieuw stelen gebruikersnaam van de gebruiker en wachtwoord of andere referenties van de lokale machine en het uitvoeren van andere kwaadaardige activiteiten.

**De formulieren exploit:**

1. De aanvaller steelt de gebruikersnaam en het wachtwoord van een van uw gebruikers.

2. De aanvaller meldt zich vervolgens aan bij het Exchange-postvak van gebruikers. De mailbox kan online in Exchange of in Exchange on-premises zijn.

3. De aanvaller maakt vervolgens een aangepaste e-mailformuliersjabloon en voegt deze in het postvak van de gebruiker in. Het aangepaste formulier wordt geactiveerd wanneer het postvak een e-mail ontvangt waarvoor het postvak het aangepaste formulier moet laden. Het aangepaste formulier en het formaat van e-mail zijn op maat gemaakt voor elkaar.
4. De aanvaller stuurt de triggere-mail naar de gebruiker, die zijn postvak normaal gebruikt.

5. Wanneer de e-mail wordt ontvangen, wordt het formulier geladen. Het formulier start een toepassing op een externe (WebDAV) server.

6. De applicatie installeert meestal malware, zoals [Powershell Empire](https://www.powershellempire.com/), lokaal op de machine van de gebruiker.

7. De malware kan de aanvaller opnieuw stelen gebruikersnaam van de gebruiker en wachtwoord of andere referenties van de lokale machine en het uitvoeren van andere kwaadaardige activiteiten.

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Wat een aanval met de injectie van regels en aangepaste formulieren lijkt mogelijk op Office 365?

Deze persistentiemechanismen zullen waarschijnlijk niet opgemerkt worden door uw gebruikers en kunnen in sommige gevallen zelfs onzichtbaar voor hen zijn. Dit artikel vertelt u hoe u moet zoeken naar een van de zeven tekens (Indicatoren van compromis) hieronder vermeld. Als u een van deze, moet u herstelstappen te nemen.

- Indicatoren van het compromis van het Reglement:

  - Regelactie is het starten van een toepassing.

  - Regel verwijst naar een EXE, ZIP of URL.

  - Zoek op de lokale machine naar nieuwe processtarts die afkomstig zijn van de Outlook PID.

- Indicatoren van het compromis voor aangepaste formulieren:

  - Aangepaste vorm die is opgeslagen als hun eigen berichtklasse.

  - Berichtklasse bevat uitvoerbare code.

  - Meestal opgeslagen in persoonlijke formulierenbibliotheek of postvak indemap.

  - Formulier heet IPM. Opmerking. [aangepaste naam].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Stappen voor het vinden van tekenen van deze aanval en het bevestigen van het

U een van deze twee methoden gebruiken om de aanval te bevestigen:

- Controleer handmatig de regels en formulieren voor elk postvak met behulp van de Outlook-client. Deze methode is grondig, maar u de gebruiker van het postvak alleen controleren op een tijdstip dat zeer tijdrovend kan zijn als u veel gebruikers hebt om te controleren. Het kan ook resulteren in een schending van de computer die u de controle van.

- Gebruik het [PowerShell-script Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) om automatisch alle regels voor het doorsturen van e-mail en aangepaste formulieren te dumpen voor alle gebruikers in uw huurovereenkomst. Dit is de snelste en veiligste methode met de minste hoeveelheid overhead.

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>De aanval op regels bevestigen met de Outlook-client

1. Open de Outlook-client voor gebruikers als gebruiker. De gebruiker kan uw hulp nodig hebben bij het onderzoeken van de regels op hun mailbox.

2. Raadpleeg [E-mailberichten beheren met het artikel Regels](https://support.office.com/article/c24f5dea-9465-4df4-ad17-a50704d66c59) voor de procedures voor het openen van de regelsinterface in Outlook.

3. Zoek naar regels die de gebruiker niet heeft gemaakt, of onverwachte regels of regels met verdachte namen.

4. Kijk in de regelbeschrijving naar regelacties die een . Exe. ZIP-bestand of om een URL te starten.

5. Zoek naar nieuwe processen die de Outlook-proces-id beginnen te gebruiken. Raadpleeg [de proces-id zoeken](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Stappen om de aanval op Formulieren te bevestigen met de Outlook-client

1. Open de Outlook-client van de gebruiker als gebruiker.

2. Volg de stappen in [Het tabblad Ontwikkelaars weergeven](https://support.office.com/article/e1192344-5e56-4d45-931b-e5fd9bea2d45) voor de gebruikersversie van Outlook.

3. Open het nu zichtbare ontwikkelaarstabblad in Outlook en klik op **een formulier ontwerpen**.

4. Selecteer het **Postvak IN** in de lijst **Zoeken in.** Zoek naar aangepaste formulieren. Aangepaste formulieren zijn zeldzaam genoeg dat als je een aangepaste formulieren op alle, het is de moeite waard een diepere blik.

5. Onderzoek alle aangepaste formulieren, met name die gemarkeerd als verborgen.

6. Open aangepaste formulieren en klik in de groep **Formulier** op **Code weergeven** om te zien wat er wordt uitgevoerd wanneer het formulier wordt geladen.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Stappen om de aanval op regels en formulieren te bevestigen met PowerShell

De eenvoudigste manier om een aanval op regels of aangepaste formulieren te verifiëren, is door het [PowerShell-script Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) uit te voeren. Dit script maakt verbinding met elk postvak in uw tenant en dumpt alle regels en formulieren in twee CSV-bestanden.

#### <a name="pre-requisites"></a>Vereisten

U moet een globale beheerdersrechten hebben om het script uit te voeren, omdat het script verbinding maakt met elk postvak in de huurovereenkomst om de regels en formulieren te lezen.

1. Meld u aan bij de machine waarvan u het script uitvoert met lokale beheerdersrechten.

2. Download of kopieer het Get-AllTenantRulesAndForms.ps1-script van GitHub naar een map waaruit je het uitvoert. Het script maakt twee datumstempelbestanden voor deze map, MailboxFormsExport-yyyy-mm-dd.csv en MailboxRulesExport-yyyy-mm-dd.csv.

3. Open een PowerShell-instantie als beheerder en open de map waarop u het script hebt opgeslagen.

4. Voer deze PowerShell-opdrachtregel als volgt uit `.\Get-AllTenantRulesAndForms.ps1` .\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>De uitvoer interpreteren

- **MailboxRulesExport-*yyyy-mm-dd*.csv**: Bekijk de regels (één per rij) voor actievoorwaarden die toepassingen of uitvoerbare artikelen bevatten:

  - **ActionType (kolom A):** Als u de waarde 'ID_ACTION_CUSTOM' ziet, is de regel waarschijnlijk kwaadaardig.

  - **IsPotentiallyMalicious (kolom D)**: Als deze waarde "WAAR" is, is de regel waarschijnlijk kwaadaardig.

  - **ActionCommand (kolom G):** Als hiermee een toepassing of een bestand met een .exe- of .zip-extensie of een item wordt vermeld dat verwijst naar een URL, die er niet hoort te zijn, is de regel waarschijnlijk kwaadaardig.

- **MailboxFormsExport-*yyyy-mm-dd*.csv**: Over het algemeen is het gebruik van aangepaste formulieren zeer zeldzaam. Als u die in deze werkmap vindt, opent u het postvak van die gebruiker en onderzoekt u het formulier zelf. Als uw organisatie niet zet het er opzettelijk, het is waarschijnlijk kwaadaardig.

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>De aanval met Outlook-regels en formulieren stoppen en herstellen

Als u enig bewijs van een van deze aanvallen, herstel is eenvoudig, verwijder gewoon de regel of formulier uit de mailbox. U dit doen met de Outlook-client of externe PowerShell gebruiken om regels te verwijderen.

### <a name="using-outlook"></a>Outlook gebruiken

1. Identificeer alle apparaten die de gebruiker met Outlook heeft gebruikt. Ze zullen allemaal moeten worden gereinigd van potentiële malware. Sta niet toe dat de gebruiker zich aanmeldt en e-mail gebruikt totdat alle apparaten zijn schoongemaakt.

2. Volg de stappen in Een regel voor elk apparaat [verwijderen.](https://support.microsoft.com/en-us/office/delete-a-rule-2f0e7139-f696-4422-8498-44846db9067f)

3. Als u niet zeker bent over de aanwezigheid van andere malware, u alle software op het apparaat opmaken en opnieuw installeren. Voor mobiele apparaten u de stappen van de fabrikant volgen om het apparaat opnieuw in te stellen op de fabrieksafbeelding.

4. Installeer de meest up-to-date versies van Outlook. Houd er rekening mee dat de huidige versie van Outlook beide typen van deze aanval standaard blokkeert.

5. Zodra alle offline kopieën van het postvak zijn verwijderd, moet u het wachtwoord van de gebruiker opnieuw instellen (gebruik een kwaliteitswachtwoord) en de stappen volgen in [Setup multi-factor authenticatie voor gebruikers](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) als MFA nog niet is ingeschakeld. Dit zorgt ervoor dat de referenties van de gebruiker niet via andere middelen worden weergegeven (zoals phishing of hergebruik van wachtwoorden).

### <a name="using-powershell"></a>PowerShell gebruiken

Er zijn twee externe PowerShell-cmdlets die u gebruiken om gevaarlijke regels te verwijderen of uit te schakelen. Volg gewoon de stappen.

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a>Stappen voor postvakken die zich op een Exchange-server bevinden

1. Maak verbinding met de Exchange-server via externe PowerShell. Volg de stappen in [Connect to Exchange-servers met behulp van externe PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. Als u één regel, meerdere regels of alle regels uit een postvak volledig wilt verwijderen, gebruikt u de cmdlet [Remove-InboxRule.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)

3. Als u de regel en de inhoud ervan wilt behouden voor verder onderzoek, gebruikt u de cmdlet [Disable-InboxRule.](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx)

#### <a name="steps-for-mailboxes-in-exchange-online"></a>Stappen voor postvakken in Exchange Online

1. Volg de stappen in [Connect to Exchange Online met PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Als u één regel, meerdere regels of alle regels uit een postvak volledig wilt verwijderen, gebruikt u de cmdlet [Voor de regel verwijderen.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)

3. Als u de regel en de inhoud ervan wilt behouden voor verder onderzoek, gebruikt u de cmdlet [Disable-InboxRule.](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx)

## <a name="how-to-minimize-future-attacks"></a>Hoe toekomstige aanvallen te minimaliseren

### <a name="first-protect-your-accounts"></a>Ten eerste: bescherm uw accounts

De exploits van Regels en formulieren worden alleen gebruikt door een aanvaller nadat deze een van de accounts van uw gebruiker heeft gestolen of geschonden. Dus, uw eerste stap om het gebruik van deze exploits tegen uw organisatie te voorkomen, is om uw gebruikersaccounts agressief te beschermen. Enkele van de meest voorkomende manieren waarop accounts worden geschonden zijn door middel van phishing of [wachtwoord spuiten](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) aanvallen.

De beste manier om uw gebruikersaccounts, en met name uw beheerdersaccounts, te beschermen, is door [multi-factor authenticatie in te stellen voor gebruikers.](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) Je moet ook:

- Controleer hoe uw gebruikersaccounts worden [geopend en gebruikt.](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) U de eerste inbreuk niet voorkomen, maar u verkort de duur en de impact van de inbreuk door deze eerder te detecteren. U dit [beveiligingsbeleid van Office 365 Cloud App](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) gebruiken om uw accounts te controleren en te waarschuwen voor ongebruikelijke activiteiten:

  - **Meerdere mislukte inlogpogingen:** dit beleid profileert uw omgeving en activeert waarschuwingen wanneer gebruikers meerdere mislukte inlogactiviteiten uitvoeren in één sessie met betrekking tot de geleerde basislijn, wat kan duiden op een poging tot schending.

  - **Onmogelijke reis:** Dit beleid profileert uw omgeving en activeert waarschuwingen wanneer activiteiten worden gedetecteerd van dezelfde gebruiker op verschillende locaties binnen een periode die korter is dan de verwachte reistijd tussen de twee locaties. Dit kan erop wijzen dat een andere gebruiker dezelfde referenties gebruikt. Het detecteren van dit afwijkende gedrag vereist een eerste leerperiode van zeven dagen waarin het het activiteitspatroon van een nieuwe gebruiker leert.

  - **Ongebruikelijke imitatieactiviteit (per gebruiker):** dit beleid profileert uw omgeving en activeert waarschuwingen wanneer gebruikers meerdere nagebootste activiteiten uitvoeren in één sessie met betrekking tot de geleerde basislijn, wat kan duiden op een poging tot schending.

- Maak gebruik van een tool zoals [Office 365 Secure Score](https://securescore.office.com/) om accountbeveiligingsconfiguraties en -gedrag te beheren.

### <a name="second-keep-your-outlook-clients-current"></a>Ten tweede: Houd uw Outlook-clients actueel

Volledig bijgewerkte en gepatchte versies van Outlook 2013 en 2016 schakelen standaard de regel/formulieractie 'Toepassing starten' uit. Dit zorgt ervoor dat, zelfs als een aanvaller het account schendt, de regel- en formulieracties worden geblokkeerd. U de nieuwste updates en beveiligingspatches installeren door de stappen in [Office-updates installeren](https://support.office.com/article/2ab296f3-7f03-43a2-8e50-46de917611c5)te volgen.

Dit zijn de patchversies voor uw Outlook 2013- en 2016-clients:

- **Outlook 2016**: 16.0.4534.1001 of hoger.

- **Outlook 2013**: 15.0.4937.1000 of hoger.

Zie voor meer informatie over de afzonderlijke beveiligingspatches:

- [Beveiligingspatch van Outlook 2016](https://support.microsoft.com/help/3191883)

- [Beveiligingspatch van Outlook 2013](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a>Derde: Uw Outlook-clients controleren

Houd er rekening mee dat zelfs met de geïnstalleerde patches en updates het mogelijk is voor een aanvaller om de lokale machineconfiguratie te wijzigen om het gedrag 'Starttoepassing' opnieuw in te schakelen. U [Geavanceerd groepsbeleidsbeheer](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) gebruiken om het lokale machinebeleid op uw klanten te controleren en af te dwingen.

U zien of 'Toepassing starten' opnieuw is ingeschakeld via een overschrijving in het register met behulp van de informatie in [Hoe het systeemregister te bekijken met behulp van 64-bits versies van Windows.](https://support.microsoft.com/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows) Controleer de volgende subsleutels:

- **Outlook 2016**:`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`

- **Outlook 2013**:`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`

Zoek naar de sleutel EnableUnsafeClientMailRules. Als deze er is en is ingesteld op 1, is de Outlook-beveiligingspatch overschreven en is de computer kwetsbaar voor de aanval formulier/regels. Als de waarde 0 is, wordt de actie Toepassing starten uitgeschakeld. Als de bijgewerkte en gepatchte versie van Outlook is geïnstalleerd en deze registersleutel niet aanwezig is, is een systeem niet kwetsbaar voor deze aanvallen.

Klanten met on-premises Exchange-installaties moeten overwegen oudere versies van Outlook te blokkeren die geen patches beschikbaar hebben. Details over dit proces vindt u in het artikel [Outlook-clientblokkering configureren](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Microsoft 365 beveiligen als een cybersecurity pro

Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen. Gebruik de [Microsoft 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Microsoft 365-tenant te implementeren.

- Taken die in de eerste 30 dagen moeten worden uitgevoerd. Deze hebben direct effect en weinig invloed op uw gebruikers.

- Taken die binnen 90 dagen moeten worden uitgevoerd. Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.

- Na 90 dagen. Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.

## <a name="see-also"></a>Zie ook:

- [Kwaadaardige Outlook-regels](https://silentbreaksecurity.com/malicious-outlook-rules/) van SilentBreak Security Post over Rules Vector biedt een gedetailleerde beoordeling van hoe de Outlook-regels.

- [MAPI over HTTP en Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) op de Sensepost-blog over Mailrule Pwnage bespreekt een tool genaamd Ruler waarmee je mailboxen exploiteren via Outlook-regels.

- [Outlook-formulieren en -shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) op de Sensepost-blog over Forms Threat Vector.

- [Liniaal Codebase](https://github.com/sensepost/ruler)

- [Liniaal indicatoren van compromis](https://github.com/sensepost/notruler/blob/master/iocs.md)
