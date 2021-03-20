---
title: Overzicht van Microsoft 365 voor bedrijfsbeveiliging voor de Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Hoe Contoso de beveiligingsfuncties van Microsoft 365 voor ondernemingen gebruikt.
ms.openlocfilehash: 31baf61011fb67fbe11394718086d73afa2bc680
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907660"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Overzicht van Microsoft 365 voor bedrijfsbeveiliging voor de Contoso Corporation

Om goedkeuring te krijgen voor de implementatie van Microsoft 365 voor ondernemingen, heeft de IT-beveiligingsafdeling van Contoso een grondige beveiligingsbeoordeling uitgevoerd. Ze hebben de volgende beveiligingsvereisten voor de cloud geïdentificeerd:

- Gebruik de sterkste verificatiemethoden voor toegang van werknemers tot cloudbronnen.
- Zorg ervoor dat pc's en mobiele apparaten op veilige manieren verbinding maken met en toegang krijgen tot toepassingen.
- Bescherm pc's en e-mail tegen malware.
- Machtigingen voor digitale assets in de cloud bepalen wie toegang heeft tot wat en wat ze kunnen doen en zijn ontworpen voor toegang tot de minste bevoegdheden
- Gevoelige en sterk gereguleerde digitale assets worden gelabeld, versleuteld en op veilige locaties opgeslagen.
- Sterk gereguleerde digitale assets zijn beveiligd met extra versleuteling en machtigingen.
- IT-beveiligingsmedewerkers kunnen de huidige beveiligingsstatus controleren vanuit centrale dashboards en een melding krijgen van beveiligingsgebeurtenissen voor snelle reactie en beperking.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Het Contoso-pad naar de beveiligings gereedheid van Microsoft 365

Contoso heeft deze stappen gevolgd om hun beveiliging voor te bereiden op de implementatie van Microsoft 365 voor ondernemingen:

1. Beheerdersaccounts voor de cloud beperken

   Contoso heeft de bestaande Ad DS-beheerdersaccounts (Active Directory Domain Services) uitgebreid beoordeeld en een reeks speciale cloudbeheerdersaccounts en -groepen ingesteld.

2. Gegevens classificeren in drie beveiligingsniveaus

   Contoso heeft de drie niveaus zorgvuldig beoordeeld en bepaald, waarmee de Microsoft 365-functies voor ondernemingsfuncties werden bepaald om de meest waardevolle gegevens te beschermen.

3. Beleid voor toegangs-, bewaar- en informatiebeveiliging voor gegevensniveaus bepalen

   Op basis van de gegevensniveaus heeft Contoso gedetailleerde vereisten bepaald om toekomstige IT-workloads te kwalificeren die naar de cloud worden verplaatst.

Als u beveiligings-best practices en Microsoft 365 voor implementatievereisten voor ondernemingen wilt volgen, hebben contoso-beveiligingsbeheerders en de IT-afdeling veel beveiligingsfuncties en -mogelijkheden geïmplementeerd, zoals in de volgende secties wordt beschreven.

## <a name="identity-and-access-management"></a>Identiteits- en toegangsbeheer 

- Specifieke hoofdbeheerdersaccounts met MFA en PIM

  In plaats van de rol van globale beheerder toe te wijzen aan dagelijkse gebruikersaccounts, heeft Contoso drie toegewezen globale beheerdersaccounts gemaakt met sterke wachtwoorden. De accounts worden beveiligd door Azure AD Multi-Factor Authentication (MFA) en Azure Active Directory (Azure AD) Privileged Identity Management (PIM). *PIM is alleen beschikbaar met Microsoft 365 E5.*

  Aanmelden met een globale beheerdersaccount wordt alleen gedaan voor specifieke beheertaken. De wachtwoorden zijn alleen bekend bij aangewezen personeelsleden en kunnen alleen worden gebruikt binnen een periode die is geconfigureerd in Azure AD PIM.

  Contoso-beveiligingsbeheerders hebben minder beheerdersrollen toegewezen aan accounts die geschikt zijn voor de taakfunctie van die IT-werknemer.

  Zie [Informatie over beheerdersrollen in Microsoft 365](/office365/admin/add-users/about-admin-roles) voor meer informatie.

- MFA voor alle gebruikersaccounts

  MFA voegt een extra beveiligingslaag toe aan het aanmeldingsproces. Gebruikers moeten een telefoongesprek, sms-bericht of app-melding op hun smartphone bevestigen nadat ze hun wachtwoord correct hebben ingesteld. Met MFA zijn Azure AD-gebruikersaccounts beveiligd tegen onbevoegde aanmelding, zelfs als een accountwachtwoord is gehackt.

   - Om u te beschermen tegen compromissen met het Microsoft 365-abonnement, vereist Contoso MFA voor alle globale beheerdersaccounts.
   - Ter bescherming tegen phishingaanvallen, waar een kwaadwillende gebruiker de referenties van een vertrouwde persoon binnen de organisatie misbruikt en schadelijke e-mails verzendt, heeft Contoso MFA ingeschakeld voor alle gebruikersaccounts, inclusief managers en leidinggevenden.

- Veiligere apparaat- en toepassingstoegang met beleid voor voorwaardelijke toegang

  Contoso gebruikt [beleid voor voorwaardelijke toegang](../security/office-365-security/microsoft-365-policies-configurations.md) voor identiteiten, apparaten, Exchange Online en SharePoint. Het beleid voor voorwaardelijke toegang voor identiteiten houdt onder meer in dat gebruikers met een hoog risico hun wachtwoord moeten wijzigen. Daarnaast kunnen klanten geen gebruikmaken van apps die moderne verificatie niet ondersteunen. Apparaatbeleid omvat onder meer de definitie van goedgekeurde apps en het eisen van conforme pc's en mobiele apparaten. Exchange Online-beleid voor voorwaardelijke toegang omvat onder meer het blokkeren van ActiveSync-clients en de installatie van Office 365-berichtversleuteling. SharePoint-beleid voor voorwaardelijke toegang omvat onder meer extra beveiliging voor gevoelige en sterk gereglementeerde sites.

- Windows Hello voor Bedrijven

  Contoso heeft [Windows Hello voor Bedrijven](/windows/security/identity-protection/hello-for-business/hello-identity-verification) geïmplementeerd om uiteindelijk geen wachtwoorden meer nodig te hebben via sterke tweestapsverificatie op pc's en mobiele apparaten met Windows 10 Enterprise.

- Windows Defender Credential Guard

  Als u gerichte aanvallen en malware die in het besturingssysteem wordt uitgevoerd met beheerdersbevoegdheden wilt blokkeren, heeft Contoso [Windows Defender Credential Guard](/windows/security/identity-protection/credential-guard/credential-guard) ingeschakeld via het AD DS-groepsbeleid.

## <a name="threat-protection"></a>Bedreigingsbeveiliging

- Bescherming tegen malware met Windows Defender Antivirus

  Contoso gebruikt [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) voor bescherming tegen malware en antimalwarebeheer voor pc's en apparaten met Windows 10 Enterprise.

- E-mailstroom- en postvakauditregistratie beveiligen met Microsoft Defender voor Office 365 

  Contoso gebruikt Exchange Online Protection en Defender voor [Office 365](/office365/securitycompliance/office-365-atp) om te beschermen tegen onbekende malware, virussen en schadelijke URL's die via e-mailberichten worden verzonden.

  Contoso heeft ook controlelogboeken voor postvakken ingeschakeld om te bepalen wie zich aanmeldt bij gebruikerspostvakken, berichten verzendt en andere activiteiten doet die worden uitgevoerd door de eigenaar van het postvak, een gedelegeerde gebruiker of een beheerder.

- Controle op en voorkoming van aanvallen met dreigingsonderzoek en -reacties in Office 365

  Contoso gebruikt Onderzoek en reactie van Bedreigingen van [Office 365](/office365/securitycompliance/office-365-ti) om gebruikers te beschermen door het eenvoudig te maken om aanvallen te identificeren en aan te pakken en toekomstige aanvallen te voorkomen.

- Bescherming tegen geavanceerde aanvallen met Advanced Threat Analytics

  Contoso gebruikt [ATA (Advanced Threat Analytics)](/advanced-threat-analytics/what-is-ata) om zichzelf te beschermen tegen geavanceerde doelgerichte aanvallen.  ATA analyseert, leert en identificeert automatisch normaal en abnormaal gedrag van entiteiten (gebruikers, apparaten en resources).

## <a name="information-protection"></a>Gegevensbescherming

- Gevoelige en sterk gereglementeerde digitale activa beschermen met Azure Information Protection-labels

  Contoso heeft drie niveaus van gegevensbescherming ingesteld en [Microsoft 365-vertrouwelijkheidslabels](../compliance/sensitivity-labels.md) geïmplementeerd die gebruikers kunnen toepassen op digitale activa. Voor de bedrijfsgeheimen en andere intellectuele eigendommen gebruikt Contoso gevoeligheidssublabels voor sterk gereguleerde gegevens. Dit proces versleutelt inhoud en beperkt de toegang tot specifieke gebruikersaccounts en -groepen.

- Gegevensverlies op intranet voorkomen met preventie van gegevensverlies

  Contoso heeft [](../compliance/data-loss-prevention-policies.md) beleid voor preventie van gegevensverlies geconfigureerd voor Exchange Online, SharePoint en OneDrive voor Bedrijven om te voorkomen dat gebruikers per ongeluk of opzettelijk gevoelige gegevens delen.

- Gegevenslekken op apparaten voorkomen met Windows-gegevensbescherming

  Contoso gebruikt [Windows Information Protection (WIP)](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) om te beschermen tegen gegevenslekken via op internet gebaseerde apps en services en enterprise-apps en gegevens op bedrijfsapparaten en persoonlijke apparaten die werknemers naar het werk brengen.

- Cloudbewaking met Microsoft Cloud App Security

  Contoso gebruikt [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) om haar cloudomgeving in kaart te brengen, het gebruik te bewaken en beveiligingsgebeurtenissen en -incidenten te detecteren. *Microsoft Cloud App Security is allen beschikbaar bij Microsoft 365 E5.*

- Apparaatbeheer met Microsoft Intune

  Contoso gebruikt [Microsoft Intune](/intune/introduction-intune) om mobiele apparaten en de apps die daarop worden uitgevoerd, te registreren, te beheren en te configureren. Beleid voor voorwaardelijke toegang voor apparaten vereist ook goedgekeurde apps en conforme pc's en mobiele apparaten.

## <a name="security-management"></a>Beveiligingsbeheer

- Centraal beveiligingsdashboard voor IT met Azure Defender

  Contoso gebruikt [Azure Defender](https://azure.microsoft.com/services/security-center/) om een geïntegreerde weergave van beveiliging en bedreigingsbeveiliging te presenteren, om beveiligingsbeleid te beheren in de werkbelastingen en om te reageren op cyberaanvallen.

- Centraal beveiligingsdashboard voor gebruikers met Windows Defender-beveiligingscentrum

  Contoso heeft de [Windows Security-app](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) geïmplementeerd op de pc's en apparaten met Windows 10 Enterprise, zodat gebruikers hun beveiligingsstatus in één oogopslag kunnen zien en actie kunnen ondernemen.