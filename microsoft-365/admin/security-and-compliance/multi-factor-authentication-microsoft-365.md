---
title: Meervoudige verificatie voor Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over multi-factor authenticatie in Microsoft 365.
ms.openlocfilehash: 128296b7dbc37ba5ebffb25a87bce589f8e5a904
ms.sourcegitcommit: 185d62f41f6b173894ba6e3e87b11b2b5d02db58
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/21/2020
ms.locfileid: "44340831"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a>Meervoudige verificatie voor Microsoft 365

Wachtwoorden zijn de meest voorkomende methode om een aanmelding bij een computer of online service te verifiëren, maar ze zijn ook het meest kwetsbaar. Mensen kunnen eenvoudige wachtwoorden kiezen en dezelfde wachtwoorden gebruiken voor meerdere aanmeldingen op verschillende computers en services.

Als u een extra beveiligingsniveau wilt bieden voor aanmeldingen, moet u multi-factor authenticatie (MFA) gebruiken, waarbij zowel een wachtwoord wordt gebruikt, dat sterk moet zijn, als een aanvullende verificatiemethode op basis van:

- Iets wat je bij je hebt dat niet gemakkelijk gedupliceerd is, zoals een smartphone.
- Iets wat je uniek en biologisch hebt, zoals je vingerafdrukken, gezicht of ander biometrisch attribuut.

De aanvullende verificatiemethode wordt pas gebruikt nadat het wachtwoord van de gebruiker is geverifieerd. Met MFA heeft de aanvaller, zelfs als een sterk gebruikerswachtwoord is gecompromitteerd, niet uw smartphone of uw vingerafdruk om de aanmelding te voltooien.

## <a name="mfa-support-in-microsoft-365"></a>MFA-ondersteuning in Microsoft 365
Standaard ondersteunen zowel Microsoft 365 als Office 365 MFA voor gebruikersaccounts met behulp van:

- Een sms-bericht dat naar een telefoon wordt verzonden waarbij de gebruiker een verificatiecode moet typen.
- Een telefoontje.
- De Microsoft Authenticator smart phone app.

In beide gevallen gebruikt de MFA-aanmelding de methode 'iets wat u bij u hebt dat niet gemakkelijk wordt gedupliceerd' voor de extra verificatie.
Er zijn meerdere manieren waarop u MFA voor Microsoft 365 en Office 365 inschakelen:

- Met beveiligingsstandaards
- Met beleid voor voorwaardelijke toegang
- Voor elk individueel gebruikersaccount (niet aanbevolen)

Deze manieren zijn gebaseerd op uw Microsoft 365-abonnement.
    
|Abonnement  |Aanbeveling  | Type klant |
|---------|---------|----------|
| Alle Microsoft 365-abonnementen | Gebruik beveiligingsstandaardinstellingen waarvoor MFA vereist is voor alle gebruikersaccounts. <br> U MFA ook per gebruikersaccount vereisen, maar dit wordt niet aanbevolen. | Kleine bedrijven |
| Microsoft 365 Business Premium <br><br> Microsoft 365 E3 <br><br> Azure Active Directory (Azure AD) Premium P1-licenties | Gebruik beleid voor voorwaardelijke toegang om MFA voor gebruikersaccounts te vereisen op basis van groepslidmaatschap, apps of andere criteria. | Kleine bedrijven naar onderneming |
| Microsoft 365 E5 <br><br> Azure AD Premium P2-licenties | Gebruik Azure AD-identiteitsbeveiliging om MFA te vereisen op basis van aanmeldingsrisicocriteria. |  Enterprise |
||||

### <a name="security-defaults"></a>Standaardinstellingen voor beveiliging

De standaardinstellingen voor beveiliging zijn een nieuwe functie voor betaalde Microsoft 365- en Office 365-abonnementen en proefabonnementen van Microsoft 365 en Office 365 die zijn gemaakt na 21 oktober 2019. Deze abonnementen hebben beveiligingsstandaardinstellingen ingeschakeld, die:

- Vereist dat al uw gebruikers MFA gebruiken met de Microsoft Authenticator-app.
- Blokkeert verouderde verificatie.

Gebruikers hebben 14 dagen de tijd om zich te registreren voor MFA met de Microsoft Authenticator-app vanaf hun smartphone. Deze periode gaat in bij de eerste aanmelding nadat de standaardinstellingen voor beveiliging zijn ingeschakeld. Na 14 dagen kunnen gebruikers zich alleen aanmelden als de MFA-registratie is voltooid.

De standaardinstellingen voor beveiliging bieden organisaties een basisbeveiligingsniveau voor gebruikersaanmeldingen dat standaard is ingeschakeld. U beveiligingsstandaardinstellingen uitschakelen ten gunste van MFA met beleid voor voorwaardelijke toegang.

U schakelt beveiligingsstandaards in of uit vanuit het deelvenster **Eigenschappen** voor Azure AD in de Azure-portal.

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

U beveiligingsstandaardinstellingen gebruiken bij elk Microsoft 365-abonnement.

Zie dit [overzicht van gevoeligheidslabels](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) voor meer informatie. 

### <a name="conditional-access-policies"></a>Beleid voor voorwaardelijke toegang

Beleidsregels voor voorwaardelijke toegang zijn regels waarmee wordt aangegeven wanneer aanmeldingen worden beoordeeld en toegestaan. U kunt bijvoorbeeld een toegangsbeleid met de volgende voorwaarden maken:

- Als de naam van het gebruikersaccount lid is van een groep gebruikers die is toegewezen aan een Exchange-, gebruikers-, wachtwoord-, beveiligings-, SharePoint- of globale beheerdersrol, wordt MFA vereist om toegang te verlenen.

Met dit beleid kunt u MFA op basis van groepslidmaatschap vereisen in plaats van dat u afzonderlijke gebruikersaccounts voor MFA gaat configureren wanneer deze worden toegewezen (of als de toewijzing ongedaan wordt gemaakt) vanuit deze beheerdersrollen.

U ook beleid voor voorwaardelijke toegang gebruiken voor meer geavanceerde mogelijkheden, zoals het vereisen van MFA voor specifieke apps of dat de aanmelding wordt gedaan vanaf een compatibel apparaat, zoals uw laptop met Windows 10.

U configureert beleid voor voorwaardelijke toegang vanuit het **beveiligingsdeelvenster** voor Azure AD in de Azure-portal.

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

U beleid voor voorwaardelijke toegang gebruiken met:

- Microsoft 365 Business Premium
- Microsoft 365 E3 en E5
- Azure AD Premium P1- en Azure AD Premium P2-licenties 

Voor kleine bedrijven met Microsoft 365 Business Premium u eenvoudig beleid voor voorwaardelijke toegang gebruiken met de volgende stappen:

1. Maak een groep met de gebruikersaccounts waarvoor MFA vereist is.
2. Schakel het MFA vereisen in voor het beleid **voor globale beheerders.**
3. Maak een op groepen gebaseerd beleid voor voorwaardelijke toegang met de volgende instellingen:
    - Toewijzingen > gebruikers en groepen: de naam van uw groep in stap 1 hierboven.
    - Opdrachten > Cloud-apps of -acties: alle cloud-apps.
    - Toegangsbesturingselementen > Grant > Grant-toegang > Vereisen meervoudige verificatie.
4. Schakel het beleid in.
5. Voeg een gebruikersaccount toe aan de groep die is gemaakt in stap 1 hierboven en test.
6. Als u MFA wilt vereisen voor extra gebruikersaccounts, voegt u deze toe aan de groep die is gemaakt in stap 1.

Met dit beleid voor voorwaardelijke toegang u de MFA-vereiste in uw eigen tempo naar uw gebruikers uitrollen.

Ondernemingen moeten [common conditional access-beleid](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) gebruiken om het volgende beleid te configureren:

- [MFA vereisen voor beheerders](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [MFA vereisen voor alle gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Verouderde verificatie blokkeren](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

Zie dit [overzicht van voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) voor meer informatie.

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection

Met Azure AD-identiteitsbeveiliging u een extra beleid voor voorwaardelijke toegang maken om [MFA te vereisen wanneer het aanmeldingsrisico gemiddeld of hoog is.](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)

U Azure AD-identiteitsbeveiliging en op risico's gebaseerdbeleid voor voorwaardelijke toegang gebruiken met:

- Microsoft 365 E5
- Azure AD Premium P2-licenties

Zie dit [overzicht van Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection) voor meer informatie.

### <a name="mfa-for-an-individual-user-account-not-recommended"></a>MFA voor een individueel gebruikersaccount (niet aanbevolen)

U moet beveiligingsstandaards of beleid voor voorwaardelijke toegang gebruiken om MFA voor aanmeldingen van uw gebruikersaccount te vereisen. Als een van deze echter niet kan worden gebruikt, raadt Microsoft MFA ten zeerste aan voor gebruikersaccounts met beheerdersrollen, met name de globale beheerdersrol, voor een abonnement van elke grootte. 

U schakelt MFA in voor afzonderlijke gebruikersaccounts vanuit het **actieve gebruikersvenster** van het Microsoft 365-beheercentrum.

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

Nadat de gebruiker zich de volgende keer aanmeldt, wordt hij gevraagd zich te registreren voor MFA en de aanvullende verificatiemethode te kiezen en te testen.

### <a name="using-these-methods-together"></a>Deze methoden samen gebruiken

In deze tabel ziet u de resultaten van het inschakelen van MFA met de standaardinstellingen voor beveiliging, het beleid voor voorwaardelijke toegang en de instellingen per gebruikersaccount.

|| Ingeschakeld | Uitgeschakeld | Secundaire verificatiemethode |
|:-------|:-----|:-------|:-------|
| **Standaardinstellingen voor beveiliging** | Kan geen beleid voor voorwaardelijke toegang gebruiken |   Kan beleid voor voorwaardelijke toegang gebruiken | De Microsoft Authenticator-app |
| **Beleidsregels voor voorwaardelijke toegang** |Als er een of meer zijn ingeschakeld, kunt u de standaardinstellingen voor beveiliging niet inschakelen | Als ze allemaal zijn uitgeschakeld, kunt u de standaardinstellingen voor beveiliging inschakelen | Door gebruiker opgegeven tijdens MFA-registratie |
| **Instelling voor account per gebruiker (niet aanbevolen)** | Overschreven door beveiligingsstandaards en beleid voor voorwaardelijke toegang waarvoor MFA vereist is | Overschreven door beveiligingsstandaards en beleid voor voorwaardelijke toegang | Door gebruiker opgegeven tijdens MFA-registratie|
||||

Als beveiligingsstandaardinstellingen zijn ingeschakeld, worden alle nieuwe gebruikers gevraagd om MFA-registratie en het gebruik van de Microsoft Authenticator-app bij hun volgende aanmelding.

Als een gebruiker echter een oudere telefoon heeft die tekstberichten kan ontvangen, maar de Microsoft Authenticator-app niet kan uitvoeren, u MFA inschakelen op dat specifieke gebruikersaccount en deze telefoon laten registreren met behulp van de aanvullende verificatiemethode voor tekstcode met de volgende stappen:

1. Beveiligingsstandaardinstellingen uitschakelen in de Azure-portal.
2. Mfa inschakelen voor het gebruikersaccount in het Microsoft 365-beheercentrum.
3. Laat de gebruiker zich aanmelden en registreren voor MFA en de verificatiemethode voor tekstcodes.
4. Als deze is voltooid, schakelt u beveiligingsstandaards in de Azure-portal in

## <a name="ways-to-manage-mfa-settings"></a>Manieren om MFA-instellingen te beheren

Er zijn twee manieren om MFA-instellingen te beheren.

In de Azure-portal u het als:

- Beveiligingsstandaardinstellingen in- en uitschakelen
- Beleid voor voorwaardelijke toegang configureren

In het Microsoft 365-beheercentrum u MFA-instellingen per gebruiker en service configureren.

## <a name="your-next-step"></a>Uw volgende stap

[MFA instellen voor Microsoft 365](set-up-multi-factor-authentication.md)

