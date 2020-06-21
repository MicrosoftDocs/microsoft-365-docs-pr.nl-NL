---
title: Subsidies voor illegale toestemming opsporen en herstellen
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Meer informatie over het herkennen en herstellen van de aanval op illegale toestemmingssubsidies in Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a324c4427046480fe81f58fc810f020c87247032
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726802"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Subsidies voor illegale toestemming opsporen en herstellen

**Samenvatting**  Meer informatie over het herkennen en herstellen van de aanval op illegale toestemmingssubsidies in Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Wat is de aanval op illegale toestemmingstoegave in Office 365?

In een aanval op een illegale toestemmingstoegeving maakt de aanvaller een azure-geregistreerde toepassing die toegang vraagt tot gegevens zoals contactgegevens, e-mail of documenten. De aanvaller trucs een eindgebruiker in het verlenen van die toepassing toestemming om toegang te krijgen tot hun gegevens, hetzij door middel van een phishing-aanval, of door het injecteren van illegale code in een vertrouwde website. Nadat de illegale toepassing toestemming heeft gekregen, heeft het toegang op accountniveau tot gegevens zonder dat er een organisatieaccount nodig is. Normale herstelstappen, zoals het resetten van wachtwoorden voor geschonden accounts of het vereisen van Multi-Factor Authentication (MFA) op accounts, zijn niet effectief tegen dit type aanval, omdat dit toepassingen van derden zijn en buiten de organisatie zijn.

Deze aanvallen maken gebruik van een interactiemodel dat ervan uitgaat dat de entiteit die de informatie aanroept, automatisering is en geen mens.

> [!IMPORTANT]
> Vermoedt u dat u problemen ondervindt met illegale toestemmingssubsidies van een app? Microsoft Cloud App Security (MCAS) heeft hulpprogramma's voor het detecteren, onderzoeken en herstellen van uw OAuth-apps. Dit MCAS-artikel heeft een tutorial die beschrijft hoe te gaan over [het onderzoeken van risicovolle OAuth apps](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth). U ook het beleid van [de OAuth-app](https://docs.microsoft.com/cloud-app-security/app-permission-policy) instellen om app-aangevraagde machtigingen te onderzoeken, welke gebruikers deze apps autoriseren en deze machtigingenaanvragen op grote schaal goed te keuren of te verbieden.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Hoe ziet een aanval op een illegale toestemmingssubsidie eruit in Office 365?

U moet het **controlelogboek** doorzoeken om tekens te vinden, ook wel Indicators of Compromise (IOC) van deze aanval genoemd. Voor organisaties met veel azure-geregistreerde toepassingen en een grote gebruikersbasis, is de beste manier om wekelijks toestemmingssubsidies voor uw organisaties te controleren.

### <a name="steps-for-finding-signs-of-this-attack"></a>Stappen voor het vinden van tekenen van deze aanval

1. Open het **Security & Compliance Center** op <https://protection.office.com> .

2. Navigeer naar **zoeken** en selecteer **Zoeken in controlelogboek**.

3. Zoek (alle activiteiten en alle gebruikers) en voer indien nodig de begin- en einddatum in en klik op **Zoeken.**

4. Klik **op Resultaten filteren** en voer Toestemming voor toepassing in het veld **Activiteit** in.

5. Klik op het resultaat om de details van de activiteit te zien. Klik **op Meer informatie** voor meer informatie over de activiteit. Controleer of IsAdminContent is ingesteld op True.

> [!NOTE]
> 
> Het kan 30 minuten tot 24 uur duren voordat de bijbehorende controlelogboekinvoer na een gebeurtenis in de zoekresultaten wordt weergegeven.
> 
> Hoe lang een controlerecord wordt bewaard en doorzoekbaar in het controlelogboek, is afhankelijk van uw Microsoft 365-abonnement en met name het type van de licentie dat aan een specifieke gebruiker is toegewezen. Zie [Controlelogboek voor](../../compliance/search-the-audit-log-in-security-and-compliance.md)meer informatie.
> 
> Als deze waarde waar is, geeft dit aan dat iemand met toegang tot global administrator mogelijk brede toegang tot gegevens heeft verleend. Als dit onverwacht is, neemt u stappen om een aanval te [bevestigen.](#how-to-confirm-an-attack)

## <a name="how-to-confirm-an-attack"></a>Hoe een aanval te bevestigen

Als u een of meer exemplaren van de hierboven vermelde IOCs hebt, moet u verder onderzoek doen om te bevestigen dat de aanval heeft plaatsgevonden. U een van deze drie methoden gebruiken om de aanval te bevestigen:

- Voorraadtoepassingen en machtigingen daarvan via de Azure Active Directory-portal. Deze methode is grondig, maar u slechts één gebruiker tegelijk controleren, wat zeer tijdrovend kan zijn als u veel gebruikers hebt om te controleren.

- Voorraadtoepassingen en hun machtigingen met PowerShell. Dit is de snelste en meest grondige methode, met de minste hoeveelheid overhead.

- Laat uw gebruikers hun apps en machtigingen individueel controleren en de resultaten rapporteren aan de beheerders voor herstel.

## <a name="inventory-apps-with-access-in-your-organization"></a>Apps inventariseren met toegang in uw organisatie

U dit voor uw gebruikers doen met de Azure Active Directory Portal of PowerShell of uw gebruikers afzonderlijk hun toepassingstoegang laten opsommen.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Stappen voor het gebruik van de Azure Active Directory Portal

U de toepassingen opzoeken waaraan elke individuele gebruiker machtigingen heeft verleend met behulp van de [Azure Active Directory Portal](https://portal.azure.com/).

1. Meld u aan bij de Azure Portal met beheerdersrechten.

2. Selecteer het Azure Active Directory-blad.

3. Selecteer **Gebruikers**.

4. Selecteer de gebruiker die u wilt controleren.

5. Selecteer **Toepassingen**.

Hiermee ziet u de apps die aan de gebruiker zijn toegewezen en welke machtigingen de toepassingen hebben.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Stappen om uw gebruikers toegang tot hun toepassing te laten opsommen

Laat uw gebruikers naar https://myapps.microsoft.com en bekijk hun eigen applicatie toegang daar. Ze moeten in staat zijn om alle apps met toegang te zien, details over hen te bekijken (inclusief de reikwijdte van de toegang), en in staat zijn om privileges in te trekken voor verdachte of illegale apps.

### <a name="steps-for-doing-this-with-powershell"></a>Stappen om dit te doen met PowerShell

De eenvoudigste manier om de Illegale Consent Grant-aanval te verifiëren, is door [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)uit te voeren, waardoor alle OAuth-toestemmingssubsidies en OAuth-apps voor alle gebruikers in uw huurovereenkomst worden in één CSV-bestand worden ingevoerd.

#### <a name="pre-requisites"></a>Pre-requirementsen

- De Azure AD PowerShell-bibliotheek is geïnstalleerd.

- Globale beheerdersrechten op de tenant waartegen het script wordt uitgevoerd.

- Lokale beheerder op de computer van waaruit de scripts worden uitgevoerd.

> [!IMPORTANT]
> We raden u ***ten zeerste aan*** om meervoudige verificatie voor uw administratieve account te vereisen. Dit script ondersteunt MFA-verificatie.

1. Meld u aan bij de computer waarvan u het script uitvoert met lokale beheerdersrechten.

2. Download of kopieer het [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script van GitHub naar een map van waaruit u het script uitvoert. Dit is dezelfde map waarop het bestand "permissions.csv" wordt geschreven.

3. Open een PowerShell-instantie als beheerder en open de map waar u het script hebt opgeslagen.

4. Maak verbinding met uw map met de [connect-AzureAD-cmdlet.](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)

5. Voer deze PowerShell-opdracht uit:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Het script produceert één bestand met de naam Permissions.csv. Volg deze stappen om te zoeken naar subsidies voor illegale aanvraagtoestemming:

1. Zoek in de kolom G (ConsentType) naar de waarde 'AllPrinciples'. Met de toestemming van AllPrincipals kan de clienttoepassing toegang krijgen tot ieders inhoud in de huurovereenkomst. Native Microsoft 365-toepassingen hebben deze toestemming nodig om correct te werken. Elke niet-Microsoft-toepassing met deze toestemming moet zorgvuldig worden beoordeeld.

2. Controleer in de kolom F (Machtiging) de machtigingen die elke gedelegeerde toepassing moet bevatten. Zoek naar toestemming voor 'Lezen' en 'Schrijven' of '*. Alle" toestemming, en controleer deze zorgvuldig omdat ze misschien niet geschikt zijn.

3. Bekijk de specifieke gebruikers die toestemming hebben verleend. Als gebruikers met een hoog profiel of een hoge impact ongepaste toestemmingen hebben verleend, moet u het verder onderzoeken.

4. Zoek in de kolom ClientDisplayName (kolom C) naar apps die verdacht lijken. Apps met verkeerd gespelde namen, super flauwe namen of hacker-klinkende namen moeten zorgvuldig worden beoordeeld.

## <a name="determine-the-scope-of-the-attack"></a>Het bereik van de aanval bepalen

Nadat u de toegang tot de voorraadtoepassing hebt voltooid, controleert u het **controlelogboek** om de volledige omvang van de inbreuk te bepalen. Zoek op de getroffen gebruikers, de termijnen die de illegale toepassing toegang had tot uw organisatie en de machtigingen die de app had. U het **controlelogboek** doorzoeken in het [Microsoft 365 Security and Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

> [!IMPORTANT]
> [Postvakcontrole](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) en [activiteitscontrole voor beheerders en gebruikers](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) moeten vóór de aanval zijn ingeschakeld om deze informatie te verkrijgen.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Hoe te stoppen en te saneren van een illegale toestemming subsidie aanval

Nadat u een toepassing met illegale machtigingen hebt geïdentificeerd, hebt u verschillende manieren om die toegang te verwijderen.

- U de machtiging van de toepassing in de Azure Active Directory Portal intrekken door:

  - Navigeer naar de getroffen gebruiker in het **Azure Active Directory User blade.**

  - Selecteer **Toepassingen**.

  - Selecteer de illegale toepassing.

  - Klik **op Verwijderen** in de inzoom.

- U de OAuth-toestemmingssubsidie met PowerShell intrekken door de stappen in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)te volgen.

- U de roltoewijzing service-app met PowerShell intrekken door de stappen in [Remove-AzureADServiceAppRoleAssignment te](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)volgen.

- U aanmelden voor het betreffende account ook helemaal uitschakelen, waardoor de toegang van apps tot gegevens in dat account wordt uitgeschakeld. Dit is natuurlijk niet ideaal voor de productiviteit van de eindgebruiker, maar als u werkt om de impact snel te beperken, kan het een levensvatbare kortetermijnsanering zijn.

- U geïntegreerde applicaties uitschakelen voor uw huur. Dit is een drastische stap die de mogelijkheid voor eindgebruikers om toestemming te verlenen op een tenant-brede basis uitschakelt. Dit voorkomt dat uw gebruikers per ongeluk toegang verlenen tot een schadelijke toepassing. Dit wordt niet sterk aanbevolen omdat het de mogelijkheid van uw gebruikers om productief te zijn met toepassingen van derden ernstig aantast. U dit doen door de stappen in Het in- of uitschakelen van [geïntegreerde apps te volgen.](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Microsoft 365 beveiligen als een cybersecurity pro

Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen. Gebruik de [Microsoft 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Microsoft 365-tenant te implementeren.

- Taken die in de eerste 30 dagen moeten worden uitgevoerd. Deze hebben direct effect en weinig invloed op uw gebruikers.

- Taken die binnen 90 dagen moeten worden uitgevoerd. Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.

- Na 90 dagen. Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.

## <a name="see-also"></a>Zie ook:

- [Onverwachte toepassing in mijn toepassingen lijst](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) loopt beheerders door middel van verschillende acties die ze willen nemen na het realiseren van er onverwachte toepassingen met toegang tot gegevens.

- [Het integreren van toepassingen met Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is een overzicht op hoog niveau van toestemming en machtigingen.

- [Problemen met het ontwikkelen van mijn applicatie](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) biedt links naar verschillende toestemming gerelateerde artikelen.

- [Hoofdobjecten voor toepassingen en services in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) bieden een overzicht van de hoofdobjecten voor toepassingen en services die de kern vormen van het toepassingsmodel.

- [De toegang tot apps beheren](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is een overzicht van de mogelijkheden die beheerders hebben om gebruikerstoegang tot apps te beheren.
