---
title: Gebruikersaanmeldingen bij uw Microsoft 365-Tenant beveiligen
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/30/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365initiative-coredeploy
ms.custom: ''
description: Vereisen dat uw gebruikers zich veilig aanmelden met meervoudige verificatie (MFA) en andere functies.
ms.openlocfilehash: 32a33822d33d5be881e02089d064866db5d8e111
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051256"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a>Gebruikersaanmeldingen bij uw Microsoft 365-Tenant beveiligen

Om de beveiliging van gebruikersaanmeldingen te vergroten:

- Windows Hello voor Bedrijven gebruiken
- Wachtwoordbeveiliging van Azure Active Directory (Azure AD) gebruiken
- Meervoudige verificatie (MFA) gebruiken
- Configuratie van identiteiten en apparaattoegang implementeren
- Beschermen tegen inbreuk op referenties met Azure AD Identity Protection

## <a name="windows-hello-for-business"></a>Windows Hello voor Bedrijven

Windows Hello voor Bedrijven in Windows 10 Enterprise vervangt wachtwoorden met sterke tweeledige verificatie bij het ondertekenen op een Windows-apparaat. De twee factoren zijn een nieuw type gebruikersreferentie dat is gekoppeld aan een apparaat en een biometrisch kenmerk of een pincode.

Zie [Overzicht Windows Hello voor Bedrijven](/windows/security/identity-protection/hello-for-business/hello-overview)voor meer informatie.


## <a name="azure-ad-password-protection"></a>Azure AD-wachtwoordbeveiliging

Azure AD-wachtwoordbeveiliging detecteert en blokkeert bekende zwakke wachtwoorden en hun varianten, en kan ook aanvullende zwakke termen blokkeren die specifiek zijn voor uw organisatie. Standaardlijsten met verboden wachtwoorden worden automatisch toegepast op alle gebruikers in een Azure AD-tenant. U kunt aanvullende vermeldingen definiëren in een aangepaste lijst met geblokkeerde wachtwoorden. Als gebruikers hun wachtwoord wijzigen of opnieuw instellen, worden deze verboden wachtwoordlijsten ingeschakeld om het gebruik van sterke wachtwoorden af te dwingen.

Zie [Azure AD-wachtwoordbeveiliging configureren](/azure/active-directory/authentication/concept-password-ban-bad)voor meer informatie.

## <a name="mfa"></a>MFA

Bij MFA is er voor gebruikersaanmeldingen extra verificatie naast het wachtwoord voor het gebruikersaccount nodig. Zelfs als kwaadwillende gebruikers het wachtwoord voor een gebruikersaccount achterhalen, moeten ze ook kunnen reageren op de extra verificatie, zoals een sms die naar een smartphone wordt gestuurd voordat er toegang wordt verleend.

![Het juiste wachtwoord plus een extra verificatie resulteert in een geslaagde aanmelding](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

De eerste stap voor het gebruik van MFA is ***om het voor alle beheerdersaccounts*** te gebruiken, ook wel geprivilegieerde accounts genoemd.

Daarnaast raadt Microsoft MFA aan voor alle gebruikers.

Er zijn drie manieren waarop u uw gebruikers kunt verplichten MFA te gebruiken op basis van uw Microsoft 365-abonnement.

| Abonnement | Aanbeveling |
|---------|---------|
|Alle Microsoft 365-abonnementen (zonder Azure AD Premium P1- of P2-licenties)     |[Schakel standaardinstellingen voor beveiliging in Azure AD in](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). De standaardinstellingen voor beveiliging in Azure AD omvatten MFA voor gebruikers en beheerders.   |
|Microsoft 365 E3 (bevat Azure AD Premium P1-licenties)     | Gebruik [algemeen beleid voor voorwaardelijke toegang](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) om het volgende beleid te configureren: <br>- [MFA vereisen voor beheerders](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [MFA vereisen voor alle gebruikers](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Verouderde verificatie blokkeren](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (bevat Azure AD Premium P2-licenties)     | Als u gebruikmaakt van Azure AD Identity Protection, begint u het implementeren van de [aanbevolen set beleidsregels voor voorwaardelijke toegang en verwante beleidsregels](../security/defender-365-security/identity-access-policies.md) van Microsoft door de volgende twee beleidsregels te maken:<br> - [MFA vereisen bij een normaal of hoog risico bij het aanmelden](../security/defender-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Gebruikers met een hoog risico moeten het wachtwoord wijzigen](../security/defender-365-security/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

### <a name="security-defaults"></a>Standaardinstellingen voor beveiliging

De standaardinstellingen voor beveiliging zijn een nieuwe functie voor betaalde Microsoft 365- en Office 365-abonnementen en proefabonnementen van Microsoft 365 en Office 365 die zijn gemaakt na 21 oktober 2019. Bij deze abonnementen zijn de standaardinstellingen voor beveiliging ingeschakeld waarmee ***al uw gebruikers MFA met de Microsoft Authenticator-app moeten gebruiken***.
 
Gebruikers hebben 14 dagen de tijd om zich te registreren voor MFA met de Microsoft Authenticator-app vanaf hun smartphone. Deze periode gaat in bij de eerste aanmelding nadat de standaardinstellingen voor beveiliging zijn ingeschakeld. Na 14 dagen kunnen gebruikers zich alleen aanmelden als de MFA-registratie is voltooid.

De standaardinstellingen voor beveiliging bieden organisaties een basisbeveiligingsniveau voor gebruikersaanmeldingen dat standaard is ingeschakeld. U kunt de standaardinstellingen voor beveiliging uitschakelen ten gunste van MFA met voorwaardelijk toegangsbeleid of voor afzonderlijke accounts.

Zie het [overzicht van standaardinstellingen voor beveiliging](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie.

### <a name="conditional-access-policies"></a>Beleidsregels voor voorwaardelijke toegang

Beleidsregels voor voorwaardelijke toegang zijn regels waarmee wordt aangegeven wanneer aanmeldingen worden beoordeeld en toegestaan. U kunt bijvoorbeeld een toegangsbeleid met de volgende voorwaarden maken:

- Als de naam van het gebruikersaccount lid is van een groep gebruikers die is toegewezen aan een Exchange-, gebruikers-, wachtwoord-, beveiligings-, SharePoint- of globale beheerdersrol, wordt MFA vereist om toegang te verlenen.

Met dit beleid kunt u MFA op basis van groepslidmaatschap vereisen in plaats van dat u afzonderlijke gebruikersaccounts voor MFA gaat configureren wanneer deze worden toegewezen (of als de toewijzing ongedaan wordt gemaakt) vanuit deze beheerdersrollen.

U kunt beleidsregels voor voorwaardelijke toegang ook gebruiken voor meer geavanceerde mogelijkheden, zoals vereisen dat de aanmelding wordt uitgevoerd vanaf een compatibel apparaat, zoals uw laptop met Windows 10.

Voor voorwaardelijke toegang zijn Azure AD Premium P1-licenties vereist, die deel uitmaken van Microsoft 365 E3 en E5.

Zie het [overzicht van voorwaardelijke toegang](/azure/active-directory/conditional-access/overview) voor meer informatie.

### <a name="using-these-methods-together"></a>Deze methoden samen gebruiken

Houd het volgende in gedachten:

- U kunt geen standaardinstellingen voor beveiliging inschakelen als er beleidsregels voor voorwaardelijke toegang zijn ingeschakeld.
- Het is niet mogelijk om beleidsregels voor voorwaardelijke toegang in te schakelen als er standaardinstellingen voor beveiliging zijn ingeschakeld.

Als de standaardinstellingen voor beveiliging zijn ingeschakeld, moeten alle nieuwe gebruikers zich voor MFA registreren en de Microsoft Authenticator-app gebruiken. 

In deze tabel ziet u de resultaten na het inschakelen van MFA met de standaardinstellingen voor beveiliging en het beleid voor voorwaardelijke toegang.

| Methode | Ingeschakeld | Uitgeschakeld | Extra verificatiemethode |
|:-------|:-----|:-------|:-------|
| **Standaardinstellingen voor beveiliging**  | Kan geen beleid voor voorwaardelijke toegang gebruiken | Kan beleid voor voorwaardelijke toegang gebruiken | De Microsoft Authenticator-app |
| **Beleidsregels voor voorwaardelijke toegang** | Als er een of meer zijn ingeschakeld, kunt u de standaardinstellingen voor beveiliging niet inschakelen | Als ze allemaal zijn uitgeschakeld, kunt u de standaardinstellingen voor beveiliging inschakelen  | Opgeven door gebruiker tijdens MFA-registratie  |
||||

## <a name="identity-and-device-access-configurations"></a>Configuratie van identiteiten en apparaattoegang

Instellingen en beleid voor identiteiten en apparaattoegang zijn aanbevolen vereiste functies. Hun instellingen in combinatie met voorwaardelijke toegang, Intune en Azure AD Identity Protection-beleidsregels bepalen of een bepaald toegangsverzoek moet worden verleend en onder welke voorwaarden. Deze bepaling is gebaseerd op het gebruikersaccount van de login, het apparaat dat wordt gebruikt, de app die de gebruiker gebruikt voor toegang, de locatie van waaruit het toegangsverzoek is gedaan en een beoordeling van het risico van de aanvraag. Op deze manier zorgt u ervoor dat alleen goedgekeurde gebruikers en apparaten toegang hebben tot uw belangrijke bronnen.

>[!Note]
>Voor Azure AD Identity Protection zijn Azure AD Premium P2-licenties vereist, die deel uitmaken van Microsoft 365 E5.
>

Beleid voor identiteiten en apparaattoegang is gedefinieerd voor gebruik in drie lagen: 

- Basisbescherming is een minimum beveiligingsniveau voor uw identiteiten en apparaten die toegang hebben tot uw apps en gegevens.
- Gevoelige bescherming biedt extra beveiliging geboden voor specifieke gegevens. Identiteiten en apparaten zijn onderhevig aan hogere niveaus van beveiliging en gezondheidseisen voor apparaten.
- Bescherming voor omgevingen met sterk gereguleerde of geclassificeerde gegevens betreft doorgaans kleine hoeveelheden gegevens die zeer vertrouwelijk zijn, handelsgeheimen bevatten of onderworpen zijn aan gegevensregelgeving. Identiteiten en apparaten zijn onderhevig aan veel hogere niveaus van beveiliging en gezondheidseisen voor apparaten. 

Deze lagen en de bijbehorende configuraties bieden een consistent beveiligingsniveau van uw gegevens, identiteiten en apparaten.

Microsoft beveelt ten zeerste aan om het beleid voor identiteits- en toegangsbeleid te configureren en in uw organisatie in te stellen, waaronder specifieke instellingen voor Microsoft Teams, Exchange Online en SharePoint. Zie voor meer informatie [Configuraties van identiteiten en apparaattoegang](../security/defender-365-security/microsoft-365-policies-configurations.md).

## <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

In dit gedeelte leert u hoe u beleidsregels configureert die bescherming bieden tegen inbreuken op referenties, waarbij een kwaadwillende gebruiker een aanval uitvoert op de accountnaam en wachtwoord van een gebruiker om toegang te krijgen tot de cloudservices en gegevens van een organisatie. Azure AD Identity Protection biedt verschillende manieren om te voorkomen dat een kwaadwillende gebruiker de referenties van een gebruikersaccount in gevaar kan brengen.

Met Azure AD Identity Protection kunt u:

|Mogelijkheid|Beschrijving|
|:---------|:---------|
| Mogelijke beveiligingslekken in de identiteiten van uw organisatie vaststellen en verhelpen | Azure AD gebruikt machine learning om afwijkingen en verdachte activiteiten te detecteren, zoals aanmeldingen en activiteiten na aanmelding. Met deze gegevens genereert Azure AD Identity Protection rapporten en waarschuwingen om u te helpen bij het evalueren van problemen en het ondernemen van actie. |
|Verdachte acties opsporen die zijn gerelateerd aan de identiteiten van uw organisatie en automatisch op deze acties reageren|U kunt beleidsregels met betrekking tot risicobeheer zodanig configureren dat deze automatisch reageren op opgespoorde problemen als een bepaald risiconiveau is bereikt. Met deze beleidsregels kunt u, naast andere besturingselementen voor voorwaardelijke toegang die worden geboden door Azure AD en Microsoft Intune, de toegang automatisch blokkeren of corrigerende acties ondernemen, waaronder wachtwoordherstel en vereiste meervoudige verificatie in Azure AD voor volgende aanmeldingen. |
| Verdachte incidenten onderzoeken en deze oplossen met beheertaken | U kunt risico gebeurtenissen onderzoeken door informatie over het beveiligingsincident te gebruiken. Er zijn eenvoudige werkstromen beschikbaar om onderzoek bij te houden en herstelbewerkingen uit te voeren, zoals het opnieuw instellen van wachtwoorden. |
|||

Zie [meer informatie over Azure AD Identity Protection](/azure/active-directory/active-directory-identityprotection).

Zie de [stappen voor het inschakelen van de Azure AD Identity Protection](/azure/active-directory/active-directory-identityprotection-enable).

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>Technische informatiebronnen voor beheerders voor MFA en beveiligde aanmeldingen

- [MFA voor Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Identiteitsroadmap voor Microsoft 365](identity-roadmap-microsoft-365.md)
- [Azure Academy Azure AD-trainingsvideo's](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Het beleid voor Azure AD Multi-Factor Authentication-registratie configureren](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [Configuratie van identiteiten en apparaattoegang](../security/defender-365-security/microsoft-365-policies-configurations.md)

## <a name="next-step"></a>Volgende stap

[Uw gebruikersaccounts beheren](manage-microsoft-365-accounts.md)