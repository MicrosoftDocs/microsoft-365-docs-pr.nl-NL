---
title: Goedkeuringsgelden voor toestemming voor studenten detecteren en herstellen
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
localization_priority: Normal
search.appverid:
- MET150
description: Meer informatie over het herkennen en herstellen van de toestemming voor de toestemming van de toestemming voor de toestemming voor de toestemming van microsoft 365 in Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a50ce58d91d2ff7b2e31e57830289c870364d9b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288285"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Goedkeuringsgelden voor toestemming voor studenten detecteren en herstellen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

**Overzicht**  Meer informatie over het herkennen en herstellen van de toestemming voor de toestemming van de gebruiker in Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Wat is een aanval van toestemming voor toestemming voor toestemming voor toestemming in Office 365?

Bij een toestemmingsverleningsaanvraag maakt de aanvaller een in Azure geregistreerde toepassing waarin toegang wordt gevraagd tot gegevens, zoals contactgegevens, e-mail of documenten. De aanvaller trucs vervolgens een eindgebruiker om die toepassing toestemming te verlenen voor toegang tot zijn gegevens via een phishing-aanval of door code in te voeren op een vertrouwde website. Nadat aan de aanvraag toestemming is verleend, heeft deze toegang op accountniveau tot gegevens zonder dat een organisatieaccount nodig is. Normale herstelstappen, zoals het opnieuw instellen van wachtwoorden voor niet-geschonden accounts of het vereisen van Multi-Factor Authentication (MFA) voor accounts, zijn niet effectief tegen dit type aanval, omdat dit toepassingen van derden zijn en van buiten de organisatie zijn.

Deze aanvallen maken gebruik van een interactiemodel dat ervan uit gaat dat de entiteit die de informatie aanroept, automatisering is en geen mens.

> [!IMPORTANT]
> Vermoedt u dat u momenteel problemen ondervindt met het verlenen van toestemming via een app? Microsoft Cloud App Security (MCAS) beschikt over hulpprogramma's voor het detecteren, onderzoeken en herstellen van uw OAuth-apps. Dit MCAS-artikel bevat een zelfstudie over het onderzoeken van risicovolle [OAuth-apps.](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth) U kunt ook [OAuth-appbeleid](https://docs.microsoft.com/cloud-app-security/app-permission-policy) instellen om door de app aangevraagde machtigingen te onderzoeken, welke gebruikers deze apps mogen beheren, en deze machtigingsaanvragen op grote schaal goed te keuren of te verbieden.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Hoe ziet een aanval van toestemming voor toestemming er in Office 365 uit?

U moet het **auditlogboek** doorzoeken om borden te vinden, ook wel Indicators of Compromise (IOC) van deze aanval genoemd. Voor organisaties met veel in Azure geregistreerde toepassingen en een groot aantal gebruikers is de beste manier om de toestemmingsaanvragen van uw organisatie wekelijks te bekijken.

### <a name="steps-for-finding-signs-of-this-attack"></a>Stappen voor het vinden van tekenen van deze aanval

1. Open het **& compliancecentrum** <https://protection.office.com> op.

2. Ga naar **Zoeken en** selecteer Zoeken in **auditlogboek.**

3. Zoek (alle activiteiten en alle gebruikers) en voer indien nodig de begin- en einddatum in en klik op **Zoeken.**

4. Klik **op Resultaten filteren** en geef Toestemming voor de toepassing op in het **veld** Activiteit.

5. Klik op het resultaat om de details van de activiteit te bekijken. Klik **op Meer informatie** voor meer informatie over de activiteit. Controleer of IsAdminContent is ingesteld op Waar.

> [!NOTE]
>
> Het kan 30 minuten tot 24 uur duren voordat de bijbehorende auditlogboekinvoer in de zoekresultaten wordt weergegeven nadat een gebeurtenis is uitgevoerd.
>
> Hoe lang een auditrecord wordt bewaard en doorzoekbaar is in het auditlogboek, is afhankelijk van uw Microsoft 365-abonnement, en met name van het type licentie dat is toegewezen aan een specifieke gebruiker. Zie Auditlogboek voor [meer informatie.](../../compliance/search-the-audit-log-in-security-and-compliance.md)
>
> Als deze waarde waar is, betekent dit dat iemand met globale beheerderstoegang algemene toegang tot gegevens heeft verleend. Als dit onverwacht is, kunt u stappen ondernemen om [een aanval te bevestigen.](#how-to-confirm-an-attack)

## <a name="how-to-confirm-an-attack"></a>Een aanval bevestigen

Als u een of meer exemplaren van de bovenstaande IOCs hebt, moet u nader onderzoek doen om te bevestigen dat de aanval heeft plaatsgevonden. U kunt een van deze drie methoden gebruiken om de aanval te bevestigen:

- Inventaris van toepassingen en hun machtigingen met behulp van de Azure Active Directory-portal. Deze methode is grondig, maar u kunt slechts één gebruiker tegelijk controleren en dit kan erg tijdrovend zijn als u veel gebruikers moet controleren.

- Inventaristoepassingen en hun machtigingen met behulp van PowerShell. Dit is de snelste en meest grondige methode, met de minste overhead.

- Laat uw gebruikers hun apps en machtigingen afzonderlijk controleren en de resultaten rapporteren aan de beheerders voor herstel.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventaris-apps met toegang in uw organisatie

U kunt dit doen voor uw gebruikers met de Azure Active Directory-portal of PowerShell, of uw gebruikers afzonderlijk hun toepassingstoegang laten opspoort.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Stappen voor het gebruik van de Azure Active Directory Portal

U kunt de toepassingen waarvoor elke individuele gebruiker machtigingen heeft verleend op zoeken met behulp van de [Azure Active Directory Portal.](https://portal.azure.com/)

1. Meld u aan bij de Azure Portal met beheerdersrechten.

2. Selecteer de Azure Active Directory-blade.

3. Selecteer **Gebruikers**.

4. Selecteer de gebruiker die u wilt controleren.

5. Selecteer **Toepassingen.**

Hier ziet u de apps die aan de gebruiker zijn toegewezen en welke machtigingen de toepassingen hebben.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Stappen voor het opsnoemen van de toepassingstoegang door uw gebruikers

Uw gebruikers daar hun https://myapps.microsoft.com eigen toepassingstoegang laten bekijken. Ze moeten alle apps met toegang kunnen zien, details over de apps kunnen bekijken (inclusief de omvang van de toegang) en de bevoegdheden voor verdachte apps of apps kunnen intrekken.

### <a name="steps-for-doing-this-with-powershell"></a>Stappen hiervoor met PowerShell

De eenvoudigste manier om de aanval van Toestemming voor toestemming voor de volgens de toestemming van de gebruiker te verifiëren, is [ doorGet-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)uit te voeren, waarmee alle OAuth-toestemmingsgelden en OAuth-apps voor alle gebruikers in uw tenancy in één CSV-bestand worden gedumpd.

#### <a name="pre-requisites"></a>Vereisten

- De Azure AD PowerShell-bibliotheek is geïnstalleerd.

- Globale beheerdersrechten voor de tenant op basis waar het script op wordt uitgevoerd.

- Lokale beheerder op de computer van waaruit de scripts worden uitgevoerd.

> [!IMPORTANT]
> U ***wordt ten zeerste*** aangeraden meervoudige verificatie voor uw beheeraccount te vereisen. Dit script ondersteunt MFA-verificatie.

1. Meld u aan bij de computer vanaf waaruit u het script wilt uitvoeren met lokale beheerdersrechten.

2. Download of kopieer het [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script van GitHub naar een map waarin u het script gaat uitvoeren. Dit is de map waarin het uitvoerbestand 'permissions.csv' wordt geschreven.

3. Open een PowerShell-exemplaar als beheerder en open het in de map waarin u het script hebt opgeslagen.

4. Maak verbinding met uw adreslijst met behulp [van de cmdlet Connect-AzureAD.](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)

5. Voer deze PowerShell-opdracht uit:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Het script produceert één bestand met de naam Permissions.csv. Volg deze stappen om te zoeken naar aanvraagmachtigingen voor studenten:

1. Zoek in de kolom ConsentType (kolom G) naar de waarde 'AllPrinciples'. Met de machtiging AllPrincipals heeft de clienttoepassing toegang tot ieders inhoud in de tenancy. Ineigen Microsoft 365-toepassingen hebben deze machtiging nodig om correct te werken. Elke niet-Microsoft-toepassing met deze machtiging moet zorgvuldig worden gecontroleerd.

2. Controleer in de kolom Machtigingen (kolom F) de machtigingen die elke gedelegeerde toepassing heeft voor de inhoud. Zoek naar de machtigingen Lezen en Schrijven of '*. Alle machtigingen en controleer deze zorgvuldig omdat ze mogelijk niet geschikt zijn.

3. Bekijk de specifieke gebruikers die toestemming hebben verleend. Als voor gebruikers met een hoge profiel- of hoge impact ongepaste toestemming is verleend, moet u nader onderzoek doen.

4. Zoek in de kolom ClientDisplayName (kolom C) naar apps die verdacht lijken. Apps met onjuist gespelde namen, superlandnamen of hackergeluidsnamen moeten zorgvuldig worden beoordeeld.

## <a name="determine-the-scope-of-the-attack"></a>De omvang van de aanval bepalen

Nadat u klaar bent met het inventariseren van de toepassingstoegang, bekijkt u het **auditlogboek** om het volledige bereik van de inbreuk te bepalen. Zoek op de betrokken gebruikers, de tijdframes die de toepassing toegang heeft tot uw organisatie en de machtigingen die de app had. U kunt het **auditlogboek doorzoeken** in het [Microsoft 365-beveiligings- en compliancecentrum.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

> [!IMPORTANT]
> [Voor het](../../compliance/enable-mailbox-auditing.md) [](../../compliance/turn-audit-log-search-on-or-off.md) verkrijgen van deze informatie moet postvakcontrole en activiteitencontrole voor beheerders en gebruikers zijn ingeschakeld vóór de aanval.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Een aanval van toestemming voor een toestemmingsverklaring stoppen en herstellen

Nadat u een toepassing met machtigingen voor uitvoering hebt geïdentificeerd, kunt u deze toegang op verschillende manieren verwijderen.

- U kunt de machtigingen van de toepassing intrekken in de Azure Active Directory Portal door:

  - Navigeer naar de betreffende gebruiker in **het Azure Active Directory User** blade.

  - Selecteer **Toepassingen.**

  - Selecteer de toepassing.

  - Klik **op Verwijderen** in het uitzoomen.

- U kunt de toestemmingsverlening voor OAuth met PowerShell intrekken door de stappen in [Remove-AzureADOAuth2Permission Wordt ingetrokken.](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)

- U kunt de toewijzing van de rol van de service-app met PowerShell intrekken door de stappen in [Remove-AzureADServiceAppRoleAssignment te volgen.](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)

- U kunt het aanmelden voor het betreffende account ook helemaal uitschakelen, zodat de app geen toegang meer heeft tot gegevens in dat account. Dit is natuurlijk niet ideaal voor de productiviteit van de eindgebruiker, maar als u het effect snel wilt beperken, kan dit een bruikbare herstel op korte termijn zijn.

- U kunt geïntegreerde toepassingen uitschakelen voor uw tenancy. Deze stap is drastisch en betekent dat eindgebruikers niet meer in staat zijn toestemming te verlenen op tenantbasis. Hiermee voorkomt u dat uw gebruikers per ongeluk toegang verlenen tot een schadelijke toepassing. Dit wordt niet sterk aanbevolen, omdat hierdoor de mogelijkheid voor gebruikers om te werken met toepassingen van derden ernstig wordt beperkt. U kunt dit doen door de stappen te volgen voor het in- of uitschakelen [van geïntegreerde apps.](../../admin/misc/user-consent.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Microsoft 365 beveiligen als een cybersecurity pro

Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen. Gebruik de [Microsoft 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Microsoft 365-tenant te implementeren.

- Taken die in de eerste 30 dagen moeten worden uitgevoerd. Deze hebben direct effect en weinig invloed op uw gebruikers.

- Taken die binnen 90 dagen moeten worden uitgevoerd. Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.

- Na 90 dagen. Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.

## <a name="see-also"></a>Zie ook:

- [Met een onverwachte toepassing in mijn lijst](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) met toepassingen worden beheerders door de diverse acties leiden die ze kunnen uitvoeren nadat ze zich realiseren dat er onverwachte toepassingen zijn met toegang tot gegevens.

- [Het integreren van toepassingen met Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is een uitgebreid overzicht van toestemming en machtigingen.

- [Problemen bij het ontwikkelen van mijn toepassing](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) bieden koppelingen naar verschillende artikelen die betrekking hebben op toestemming.

- [Toepassings- en service-principalobjecten in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) bieden een overzicht van de Application and Service principal-objecten die belangrijk zijn voor het toepassingsmodel.

- [Toegang tot apps beheren](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is een overzicht van de mogelijkheden die beheerders hebben om de gebruikerstoegang tot apps te beheren.
