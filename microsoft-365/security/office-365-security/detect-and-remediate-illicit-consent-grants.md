---
title: Illegale toestemmingsgelden detecteren en herstellen
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
description: Meer informatie over het herkennen en herstellen van de illegale toestemmingsinfarcten in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cb3ccfbb921c106b671c4409bb95bd200f0efb55
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083006"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Illegale toestemmingsgelden detecteren en herstellen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Overzicht**  Meer informatie over het herkennen en herstellen van de illegale toestemmingsinfarcten in Microsoft 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-microsoft-365"></a>Wat is de illegale toestemmingsinfarct in Microsoft 365?

Bij een illegale toestemmingsaanvraag maakt de aanvaller een azure-geregistreerde toepassing waarin toegang wordt gevraagd tot gegevens, zoals contactgegevens, e-mail of documenten. De aanvaller trucs vervolgens een eindgebruiker om die toepassing toestemming te geven om toegang te krijgen tot hun gegevens via een phishing-aanval of door illegale code in te voeren op een vertrouwde website. Nadat toestemming is verleend voor de illegale toepassing, heeft deze toegang op accountniveau tot gegevens zonder dat er een organisatieaccount nodig is. Normale herstelstappen, zoals het opnieuw instellen van wachtwoorden voor inbreukmakende accounts of het vereisen van MFA (Multi-Factor Authentication) op accounts, zijn niet effectief tegen dit type aanval, omdat dit toepassingen van derden zijn en buiten de organisatie vallen.

Deze aanvallen maken gebruik van een interactiemodel dat ervan uit gaat dat de entiteit die de informatie aanroept, automatisering is en geen mens.

> [!IMPORTANT]
> Vermoedt u dat u op dit moment problemen ondervindt met illegale toestemmingsgelden vanuit een app? Microsoft Cloud App Security (MCAS) beschikt over hulpprogramma's voor het detecteren, onderzoeken en corrigeren van uw OAuth-apps. Dit MCAS-artikel bevat een zelfstudie over het onderzoeken van riskante [OAuth-apps.](/cloud-app-security/investigate-risky-oauth) U kunt ook [OAuth-appbeleid](/cloud-app-security/app-permission-policy) instellen om te onderzoeken welke machtigingen voor apps zijn aangevraagd, welke gebruikers deze apps mogen gebruiken en deze machtigingsaanvragen op grote schaal goed te keuren of te verbieden.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-microsoft-365"></a>Hoe ziet een illegale toestemmingsinfarct eruit in Microsoft 365?

U moet in het **auditlogboek** zoeken naar tekens, ook wel Indicatoren van compromis (IOC) van deze aanval genoemd. Voor organisaties met veel azure-geregistreerde toepassingen en een grote gebruikersbasis is het de beste manier om uw toestemmingsaanvragen voor organisaties wekelijks te bekijken.

### <a name="steps-for-finding-signs-of-this-attack"></a>Stappen voor het vinden van tekenen van deze aanval

1. Open de **Microsoft 365 Defender portal bij** en selecteer <https://security.microsoft.com> audit.  Of als u rechtstreeks naar de pagina **Controle wilt** gaan, gebruikt <https://security.microsoft.com/auditlogsearch> u .

2. Controleer op **de** pagina Controle of **het** tabblad Zoeken is geselecteerd en configureer vervolgens de volgende instellingen:
   - **Datum- en tijdbereik**
   - **Activiteiten:** Controleer of **Resultaten voor alle activiteiten tonen** is geselecteerd.

   Wanneer u klaar bent, klikt u op **Zoeken**.

3. Klik op **de kolom** Activiteit om de resultaten te sorteren en te zoeken naar Toestemming **voor toepassing.**

4. Selecteer een item in de lijst om de details van de activiteit te bekijken. Controleer of IsAdminContent is ingesteld op Waar.

> [!NOTE]
>
> Het kan 30 minuten tot 24 uur duren voordat de bijbehorende controlelogboekinvoer wordt weergegeven in de zoekresultaten nadat er een gebeurtenis plaatsvindt.
>
> De duur van een auditrecord die in het auditlogboek wordt bewaard en doorzoekbaar is, is afhankelijk van uw Microsoft 365-abonnement, en met name van het type licentie dat aan een specifieke gebruiker is toegewezen. Zie [Auditlogboek](../../compliance/search-the-audit-log-in-security-and-compliance.md)voor meer informatie.
>
> Als deze waarde waar is, geeft deze aan dat iemand met globale beheerderstoegang mogelijk uitgebreide toegang tot gegevens heeft verleend. Als dit onverwacht is, moet u stappen ondernemen om [een aanval te bevestigen.](#how-to-confirm-an-attack)

## <a name="how-to-confirm-an-attack"></a>Een aanval bevestigen

Als u een of meer exemplaren van de IOC's hierboven hebt vermeld, moet u verder onderzoek doen om positief te bevestigen dat de aanval heeft plaatsgevonden. U kunt een van deze drie methoden gebruiken om de aanval te bevestigen:

- Voorraadtoepassingen en hun machtigingen met de Azure Active Directory portal. Deze methode is grondig, maar u kunt slechts één gebruiker tegelijk controleren, wat erg tijdrovend kan zijn als u veel gebruikers hebt om te controleren.
- Inventaristoepassingen en hun machtigingen met PowerShell. Dit is de snelste en meest grondige methode, met de minste hoeveelheid overhead.
- Laat uw gebruikers afzonderlijk hun apps en machtigingen controleren en de resultaten rapporteren aan de beheerders voor herstel.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventaris-apps met toegang in uw organisatie

U kunt dit doen voor uw gebruikers met de Azure Active Directory Portal of PowerShell of uw gebruikers afzonderlijk hun toepassingstoegang laten opsnoemen.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Stappen voor het gebruik van Azure Active Directory portal

U kunt de toepassingen op zoeken waaraan elke afzonderlijke gebruiker machtigingen heeft verleend met behulp van de Azure Active Directory Portal op <https://portal.azure.com> .

1. Meld u aan bij de Azure-portal met beheerdersrechten.
2. Selecteer het Azure Active Directory blad.
3. Selecteer **Gebruikers**.
4. Selecteer de gebruiker die u wilt controleren.
5. Selecteer **Toepassingen**.

Hier ziet u de apps die aan de gebruiker zijn toegewezen en welke machtigingen de toepassingen hebben.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Stappen voor het opsnoemen van de toepassingstoegang van uw gebruikers

Laten uw gebruikers hun <https://myapps.microsoft.com> eigen toepassingstoegang daar bekijken. Ze moeten alle apps met toegang kunnen zien, details ervan kunnen bekijken (inclusief het bereik van toegang) en bevoegdheden kunnen intrekken voor verdachte of illegale apps.

### <a name="steps-for-doing-this-with-powershell"></a>Stappen om dit te doen met PowerShell

De eenvoudigste manier om de aanval van de illegale toestemmingsbeurs te [ verifiëren, ](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)is doorGet-AzureADPSPermissions.ps1uit te voeren, waardoor alle OAuth-toestemmingslening en OAuth-apps voor alle gebruikers in uw huurperiode in één .csv bestand worden opgeslagen.

#### <a name="pre-requisites"></a>Vereisten

- De Azure AD PowerShell-bibliotheek is geïnstalleerd.
- Globale beheerdersrechten voor de tenant waar het script tegen wordt uitgevoerd.
- Lokale beheerder op de computer waaruit de scripts worden uitgevoerd.

> [!IMPORTANT]
> We ***raden u ten*** zeerste aan dat u meervoudige verificatie voor uw beheeraccount nodig hebt. Dit script ondersteunt MFA-verificatie.

1. Meld u aan bij de computer waaruit u het script wilt uitvoeren met lokale beheerdersrechten.

2. Download of kopieer het [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script van GitHub naar een map waaruit u het script gaat uitvoeren. Dit is dezelfde map waarop het uitvoerbestand 'permissions.csv' wordt geschreven.

3. Open een PowerShell-sessie als beheerder en open de map waarin u het script hebt opgeslagen.

4. Verbinding maken naar uw adreslijst met de [Verbinding maken-AzureAD-cmdlet.](/powershell/module/azuread/connect-azuread)

5. Voer deze PowerShell-opdracht uit:

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Het script produceert één bestand met de naam Permissions.csv. Volg deze stappen om te zoeken naar onrechtmatige machtigingen voor toepassingen:

1. Zoek in de kolom ConsentType (kolom G) naar de waarde 'AllPrinciples'. Met de machtiging AllPrincipals heeft de clienttoepassing toegang tot de inhoud van iedereen in de huurperiode. Voor Microsoft 365 toepassingen is deze machtiging nodig om correct te kunnen werken. Elke niet-Microsoft-toepassing met deze machtiging moet zorgvuldig worden gecontroleerd.

2. Controleer in de kolom Machtiging (kolom F) de machtigingen die elke gedelegeerde toepassing heeft voor inhoud. Zoek naar de machtiging 'Lezen' en 'Schrijven' of '*. Alle" machtigingen en controleer deze zorgvuldig omdat ze mogelijk niet geschikt zijn.

3. Controleer de specifieke gebruikers die toestemming hebben verleend. Als gebruikers met een hoog profiel of hoge impact ongepaste toestemmingen hebben verleend, moet u dit nader onderzoeken.

4. Zoek in de kolom ClientDisplayName (kolom C) naar apps die verdacht lijken. Apps met verkeerd gespelde namen, super saaie namen of hacker-klinkende namen moeten zorgvuldig worden gecontroleerd.

## <a name="determine-the-scope-of-the-attack"></a>Het bereik van de aanval bepalen

Nadat u klaar bent met het inventariseren van toepassingstoegang, bekijkt u het **auditlogboek** om het volledige bereik van de inbreuk te bepalen. Zoek op de getroffen gebruikers, de tijdframes die de illegale toepassing toegang had tot uw organisatie en de machtigingen die de app had. U kunt het **auditlogboek doorzoeken** in [de Microsoft 365 Defender portal.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

> [!IMPORTANT]
> [Postvakcontrole en](../../compliance/enable-mailbox-auditing.md) [Activiteitenaudit voor beheerders](../../compliance/turn-audit-log-search-on-or-off.md) en gebruikers moeten zijn ingeschakeld vóór de aanval, zodat u deze informatie kunt krijgen.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Een illegale toestemmingsverklaring stoppen en herstellen

Nadat u een toepassing met illegale machtigingen hebt geïdentificeerd, kunt u deze toegang op verschillende manieren verwijderen.

- U kunt de machtiging van de toepassing intrekken in de Azure Active Directory portal door:
  1. Ga naar de betreffende gebruiker in het **Azure Active Directory Gebruikersblad.**
  2. Selecteer **Toepassingen**.
  3. Selecteer de illegale toepassing.
  4. Klik **op Verwijderen** in de inzoomen.

- U kunt de toestemmingslening voor OAuth met PowerShell intrekken door de stappen in [Remove-AzureADOAuth2PermissionGrant te volgen.](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)

- U kunt de functietoewijzing voor service-apps intrekken met PowerShell door de stappen in [Remove-AzureADServiceAppRoleAssignment te volgen.](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)

- U kunt de aanmelding voor het betreffende account ook helemaal uitschakelen, waardoor de toegang van apps tot gegevens in dat account wordt uitgeschakeld. Dit is natuurlijk niet ideaal voor de productiviteit van de eindgebruiker, maar als u de impact snel wilt beperken, kan dit een goede oplossing zijn voor de korte termijn.

- U kunt geïntegreerde toepassingen uitschakelen voor uw huurperiode. Dit is een drastische stap die eindgebruikers de mogelijkheid uitwijst om toestemming te verlenen op tenantbasis. Hiermee voorkomt u dat uw gebruikers per ongeluk toegang verlenen tot een schadelijke toepassing. Dit wordt niet sterk aanbevolen, omdat het de mogelijkheid van uw gebruikers om productief te zijn met toepassingen van derden ernstig schaadt. U kunt dit doen door de stappen te volgen in [Geïntegreerde apps in- of uitschakelen.](../../admin/misc/user-consent.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Microsoft 365 beveiligen als een cybersecurity pro

Uw Microsoft 365-abonnement heeft een krachtige reeks aan beveiligingsmogelijkheden die u kunt gebruiken om uw gegevens en gebruikers te beschermen. Gebruik de [Microsoft 365-roadmap voor beveiliging - Topprioriteiten voor de eerste 30 dagen, 90 dagen en verder](security-roadmap.md) om door Microsoft aanbevolen procedures voor het beveiligen van uw Microsoft 365-tenant te implementeren.

- Taken die in de eerste 30 dagen moeten worden uitgevoerd. Deze hebben direct effect en weinig invloed op uw gebruikers.
- Taken die binnen 90 dagen moeten worden uitgevoerd. Deze nemen qua planning en implementatie iets meer tijd in beslag, maar zorgen voor aanzienlijke verbeteringen in uw beveiligingspostuur.
- Na 90 dagen. Deze verbeteringen zijn gebaseerd op de eerste 90 dagen.

## <a name="see-also"></a>Zie ook

- [Onverwachte toepassing in mijn lijst met toepassingen](/azure/active-directory/application-access-unexpected-application) laat beheerders verschillende acties zien die ze mogelijk willen uitvoeren nadat ze zich realiseren dat er onverwachte toepassingen zijn met toegang tot gegevens.
- [Het integreren van toepassingen Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) is een overzicht op hoog niveau van toestemming en machtigingen.
- [Problemen met het ontwikkelen van mijn toepassing](/azure/active-directory/active-directory-application-dev-development-content-map) bevat koppelingen naar verschillende artikelen met betrekking tot toestemming.
- [Toepassings- en serviceprincipaalobjecten in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) bieden een overzicht van de hoofdobjecten Toepassing en Service die de kern van het toepassingsmodel zijn.
- [Toegang tot apps beheren](/azure/active-directory/active-directory-managing-access-to-apps) is een overzicht van de mogelijkheden die beheerders hebben om gebruikerstoegang tot apps te beheren.
