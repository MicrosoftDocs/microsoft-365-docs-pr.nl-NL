---
title: Het detecteren en herstellen van illegale toestemming subsidies
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
description: Lees hoe u met de illegale toestemming een aanval kunt doorvoeren in Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 125ebdf8b3d17e3a14abec8154129b0144928905
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652955"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Het detecteren en herstellen van illegale toestemming subsidies

**Overzicht**  Lees hoe u met de illegale toestemming een aanval kunt doorvoeren in Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Wat is de ongeoorloofde toestemming een aanval verlenen in Office 365?

In een illegale toestemming vermoeden, maakt de aanvaller een Azure-geregistreerde toepassing die toegang vraagt tot gegevens zoals contactgegevens, e-mail of documenten. De kwaadwillende gebruiker leidt vervolgens een uitgebrachte persoon een uitgaand persoon om zijn of haar gegevenstoegang te verlenen via een phishing-aanval, of door het invoeren van illegale code in een vertrouwde website. Nadat aan de illegale toepassing toestemming is verleend, heeft de toepassing toegang tot gegevens op het account niveau zonder dat u een organisatieaccount hoeft te gebruiken. Gangbare herstel stappen, zoals het opnieuw instellen van wachtwoorden voor schendingen of het vereisen van meervoudige verificatie (MFA) voor accounts, zijn niet van toepassing op dit soort aanval, aangezien dit de toepassingen van derden zijn en buiten de organisatie.

Deze aanvallen profiteren van een interactie model waarbij wordt vermoed dat de persoon die de gegevens oproept, automatisering heeft en niet voor menselijke.

> [!IMPORTANT]
> Vermoedt u dat u problemen ondervindt met een onrechtse instemming-subsidies van een app, nu? Microsoft Cloud app Security (MCAS) bevat hulpmiddelen voor het detecteren, onderzoeken en herstellen van de OAuth-apps. Dit MCAS-artikel bevat een zelfstudie waarmee u kunt nagaan hoe u aan de slag met [riskive OAuth-apps](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth). U kunt ook [OAuth-app-beleidsregels](https://docs.microsoft.com/cloud-app-security/app-permission-policy) instellen voor het onderzoeken van door de gebruiker gevraagde machtigingen, welke gebruikers worden geautoriseerd voor deze apps en moeten deze machtigingen aanvragen algemeen goedkeuren.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Wat biedt een niet-illegale toestemming een aanval zoals in Office 365?

U moet in het **auditlogboek** zoeken naar tekenen, ook wel indicators van compromis (IOC) van deze aanval. Voor organisaties met veel in azure geregistreerde toepassingen en een grote gebruikersbasis dient u de vergunningen voor uw organisatie op een wekelijkse basis te beoordelen.

### <a name="steps-for-finding-signs-of-this-attack"></a>Stappen voor het vinden van tekenen van deze aanval

1. Open het **beveiligings & nalevings centrum** op <https://protection.office.com> .

2. Ga naar **zoeken** en selecteer **Zoeken in audit logboek**.

3. Zoek (alle activiteiten en alle gebruikers) en voer zo nodig de begin-en einddatum in en klik op **zoeken**.

4. Klik op **resultaten filteren** en typ instemming met de toepassing in het veld **activiteit** .

5. Klik op het resultaat om de gegevens van de activiteit te bekijken. Klik op **meer informatie** om meer informatie over de activiteit te vinden. Kijk of IsAdminContent is ingesteld op waar.

> [!NOTE]
>
> Het duurt maximaal 30 minuten tot 24 uur voordat de bijbehorende auditlogboek vermelding wordt weergegeven in de zoekresultaten nadat een gebeurtenis zich heeft voorgedaan.
>
> De tijdsduur die een audit record behoudt en kan worden doorzocht in het controlelogboek, afhankelijk van uw Microsoft 365-abonnement, en specifiek het type licentie dat is toegewezen aan een specifieke gebruiker. Zie [audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md)voor meer informatie.
>
> Als deze waarde waar is, is het mogelijk dat iemand met een globale beheerder toegang toegang heeft verleend tot gegevens. Ga als volgt te werk om [een aanval te bevestigen](#how-to-confirm-an-attack).

## <a name="how-to-confirm-an-attack"></a>Een aanval bevestigen

Als u een of meer exemplaren van de bovenstaande IOCs hebt genoemd, moet u verder onderzoek doen om te bevestigen dat de aanval heeft plaatsgevonden. U kunt een van deze drie methoden gebruiken om de aanval te bevestigen:

- Inventarisatie toepassingen en hun machtigingen via de Azure Active Directory-Portal. Deze methode is uitgebreid, maar u kunt maar één gebruiker tegelijk controleren, wat veel tijd in beslag kan zijn als u veel gebruikers wilt controleren.

- Inventarisatie toepassingen en hun machtigingen met behulp van PowerShell. Dit is de snelste en meest uitgebreide methode met het kleinste bedrag van de overhead.

- Laat uw gebruikers hun apps en machtigingen afzonderlijk controleren en rapporteer de resultaten van de beheerders voor herstel.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventarisatie van apps met toegang in uw organisatie

U kunt dit doen voor uw gebruikers met de Azure Active Directory-portal of PowerShell, of als uw gebruikers de toegang tot de toepassing afzonderlijk inventariseren.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Stappen voor het gebruik van de Azure Active Directory-Portal

Met de [Azure Active Directory-Portal](https://portal.azure.com/)kunt u de toepassingen opzoeken waarmee een individuele gebruiker machtigingen heeft verleend.

1. Meld u aan bij de Azure-Portal met beheerdersrechten.

2. Selecteer het Azure Active Directory-blad.

3. Selecteer **Gebruikers**.

4. Selecteer de gebruiker die u wilt beoordelen.

5. Selecteer **toepassingen**.

U ziet nu de apps die zijn toegewezen aan de gebruiker en welke machtigingen de toepassingen hebben.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Stappen voor het doorvoeren van de toepassing van de gebruikers

Laat uw gebruikers https://myapps.microsoft.com hier hun eigen toepassings toegang gaan raadplegen. De persoon moet alle apps kunnen zien met Access, Details over de apps (waaronder de reikwijdte) kunnen zien en machtigingen kunnen intrekken voor verdachte of ongeoorloofde apps.

### <a name="steps-for-doing-this-with-powershell"></a>Stappen om dit te doen met PowerShell

De eenvoudigste manier om na te gaan of een aanval moet worden uitgevoerd, is het uitvoeren van [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), waarbij alle OAuth-instemming met uitgaand en OAuth worden gedumpt voor alle gebruikers in uw pacht in één. CSV-bestand.

#### <a name="pre-requisites"></a>Vereisten

- De Azure AD PowerShell-bibliotheek is geïnstalleerd.

- Globale beheerdersrechten voor de Tenant waarmee het script wordt uitgevoerd.

- Lokale beheerder op de computer van waaraf de scripts worden uitgevoerd.

> [!IMPORTANT]
> U wordt ***ten zeerste aangeraden*** verificatie met meerdere factoren te vereisen voor uw beheerdersaccount. Dit script ondersteunt MFA-verificatie.

1. Meld u aan bij de computer waarop u het script wilt uitvoeren met lokale beheerdersrechten.

2. Download of kopieer het [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) -script van github naar een map waaruit u het script wilt uitvoeren. Dit is de map waarnaar de uitvoer ' permissions.csv ' bestand wordt geschreven.

3. Open een PowerShell-exemplaar als beheerder en open de map waarin u het script hebt opgeslagen.

4. Maak verbinding met uw adreslijst via de cmdlet [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) .

5. Voer deze PowerShell-opdracht uit:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Het script levert één bestand met de naam Permissions.csv op. Voer de volgende stappen uit om te zoeken naar illegale subsidies voor toepassingsmachtigingen:

1. Zoek in de kolom ConsentType (kolom G) de waarde ' AllPrinciples '. Met de machtiging AllPrincipals is de clienttoepassing toegestaan toegang te krijgen tot de inhoud van iedereen in de pacht. Voor ingebouwde Microsoft 365-toepassingen is deze machtiging nodig om goed te werken. Voor elke niet-Microsoft-toepassing waarvan deze machtiging dient te worden gecontroleerd, moet u zorgvuldig doorgaan.

2. In de kolom machtiging (kolom F) controleert u de machtigingen die zijn toegewezen aan de inhoud van een gedelegeerde toepassing. Kijk of u de machtiging lezen en schrijven hebt of *. Iedereen, en controleer de machtigingen, omdat ze mogelijk niet correct zijn.

3. Bekijk de specifieke gebruikers die zijn gemachtigd. Als uw gebruikers met een hoog profiel of veel impact gebruikers ongepaste machtigingen hebben, moet u verder onderzoek doen.

4. Zoek in de kolom ClientDisplayName (kolom C) naar apps die verdacht zijn. Apps met onjuist gespelde namen, super saai uitziet namen of hacker-geluids namen moeten zorgvuldig worden gecontroleerd.

## <a name="determine-the-scope-of-the-attack"></a>Het bereik van de aanval vaststellen

Wanneer u klaar bent met de toegang tot de toepassing voor inventarisatie, controleert u het **controlelogboek** om het volledige bereik van de schending te bepalen. Zoek op de desbetreffende gebruikers, de tijd kozijnen dat de illegale toepassing toegang heeft tot uw organisatie en de machtigingen van de app. U kunt zoeken in het **auditlogboek** in het [Microsoft 365-Beveiligingscentrum en compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

> [!IMPORTANT]
> [Postvak controle](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) en [activiteiten controle voor beheerders en gebruikers](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) moeten zijn ingeschakeld voordat u deze informatie ontvangt.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Het beëindigen en herstellen van een aanval door illegale toestemming verlenen

Nadat u hebt vastgesteld dat u een toepassing hebt met de machtiging illegaal, hebt u verschillende manieren om die toegang te verwijderen.

- U kunt de machtiging van de toepassing in de Azure Active Directory-Portal intrekken door:

  - Ga naar de desbetreffende gebruiker in de **Azure Active Directory-gebruikers** Blading.

  - Selecteer **toepassingen**.

  - Selecteer de ongeoorloofde toepassing.

  - Klik op **verwijderen** in het detailniveau.

- U kunt de OAuth-toestemming verlenen met PowerShell door de stappen te volgen in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).

- U kunt de toewijzing van de service-app met PowerShell intrekken door de stappen te volgen in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).

- U kunt de aanmelding voor het desbetreffende account ook uitschakelen, wat wil zeggen dat de app toegang tot gegevens in dat account wordt uitgeschakeld. Dit is niet ideaal voor de productiviteit van de eindgebruiker, uiteraard, maar als u de impact snel wilt beperken, kan dit een levensvatbare herbemiddeling voor korte termijn zijn.

- U kunt geïntegreerde toepassingen uitschakelen voor uw pacht. Dit is een ingrijpende stap waarmee de mogelijkheid voor eindgebruikers toestemming kan verlenen voor de gehele Tenant. Hiermee voorkomt u dat gebruikers per ongeluk toegang tot een kwaadaardige toepassing verlenen. Dit wordt niet sterk aanbevolen omdat de mogelijkheid van de gebruikers moeilijk te zijn om productief te zijn met toepassingen van derden. U kunt dit doen door de stappen uit te voeren om [geïntegreerde apps in of uit te schakelen](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Microsoft 365 beveiligen als een cybersecurity pro

Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen. Gebruik de [Microsoft 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Microsoft 365-tenant te implementeren.

- Taken die in de eerste 30 dagen moeten worden uitgevoerd. Deze hebben direct effect en weinig invloed op uw gebruikers.

- Taken die binnen 90 dagen moeten worden uitgevoerd. Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.

- Na 90 dagen. Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.

## <a name="see-also"></a>Zie ook:

- [Onverwachte aanvraag in de lijst mijn toepassingen](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) helpt beheerders bij het maken van verschillende acties die ze kunnen ondernemen na realisatie van onverwachte toepassingen met toegang tot gegevens.

- Het [integreren van toepassingen met Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is een algemeen overzicht van toestemming en machtigingen.

- [Problemen bij het ontwikkelen van de toepassing](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) biedt koppelingen naar de verschillende artikelen over de instemming.

- [Toepassings-en Service-Principal-objecten in azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) biedt een overzicht van de toepassing en Service-Principal-objecten die Core voor het toepassingsmodel zijn.

- [Toegang tot apps beheren](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is een overzicht van de functies die beheerders kunnen gebruiken voor het beheren van gebruikers toegang tot apps.
