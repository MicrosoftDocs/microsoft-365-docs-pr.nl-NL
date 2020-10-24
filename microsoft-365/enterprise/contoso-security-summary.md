---
title: Overzicht van Microsoft 365 for Enterprise Security voor Contoso Corporation
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
description: Hoe contoso gebruikmaakt van de beveiligingsfuncties van Microsoft 365 for Enterprise.
ms.openlocfilehash: d84b1423497a6a4358142902c4e159cc54b3500b
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754230"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Overzicht van Microsoft 365 for Enterprise Security voor Contoso Corporation

Als u de implementatie van Microsoft 365 for Enterprise wilt goedkeuren, heeft de afdeling IT-beveiliging contoso een uitgebreide beveiligings beoordeling uitgevoerd. Ze hebben de volgende beveiligingsvereisten voor de Cloud geïdentificeerd:

- Gebruik de krachtigste verificatiemethoden voor de toegang van werknemer tot Cloud bronnen.
- Zorg ervoor dat Pc's en mobiele apparaten op veilige wijze verbinding hebben met toepassingen.
- Beveilig Pc's en e-mail via malware.
- Machtigingen voor digitale assets op basis van de Cloud definiëren wie toegang kan krijgen tot wat en wat ze kunnen doen, en zijn ontworpen voor toegang met minimale bevoegdheden
- Gevoelige en sterk gereglementeerde digitale assets worden gelabeld, versleuteld en opgeslagen op veilige locaties.
- Nadrukkelijk gereglementeerde digitale activa zijn beschermd met extra versleuteling en machtigingen.
- IT-beveiligingspersoneel kan de huidige beveiligings Posture van Central dashboards bewaken en meldingen ontvangen over beveiligingsgebeurtenissen om snel te kunnen reageren en te beperken.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Het contoso-pad naar Microsoft 365 Security Readiness

Contoso Volg deze stappen om de beveiliging voor te bereiden op de implementatie van Microsoft 365 for Enterprise:

1. Beheerdersaccounts voor de Cloud beperken

   Contoso deed een uitgebreide controle af van de bestaande beheerdersaccounts van Active Directory Domain Services (AD DS), en het instellen van toegewezen Cloud beheerdersaccounts en groepen.

2. Gegevens in drie beveiligingsniveaus classificeren

   Contoso deed een zorgvuldig onderzoek en heeft de drie niveaus vastgesteld die zijn gebruikt om de Microsoft 365 for Enterprise-functies te identificeren om de meest waardevolle gegevens te beschermen.

3. Beleidsregels voor toegang, behoud en informatiebescherming bepalen voor gegevensniveaus

   Op basis van de gegevensniveaus heeft Contoso de uitgebreide vereisten vastgesteld voor het voldoen aan toekomstige IT-werkbelastingen die naar de cloud worden verplaatst.

Als u aanbevolen procedures voor de beveiliging en Microsoft 365 wilt volgen, gelden voor beveiligingsbeheerders van Contoso en de IT-afdeling diverse beveiligingsfuncties en-functies, zoals beschreven in de volgende secties.

## <a name="identity-and-access-management"></a>Identiteits- en toegangsbeheer 

- Specifieke hoofdbeheerdersaccounts met MFA en PIM

  In plaats van de globale beheerdersrol toe te wijzen aan dagelijkse gebruikersaccounts, is contoso drie toegewezen globale beheerdersaccounts gemaakt met sterke wachtwoorden. De accounts zijn beveiligd via Azure multi-factor Authentication (MFA) en Azure Active Directory (Azure AD) met geprivilegieerde identiteitsbeheer (PIM). *PIM is alleen beschikbaar met Microsoft 365 E5.*

  Wanneer u zich aanmeldt met een account van een globale beheerder, wordt alleen rekening gemaakt voor specifieke beheertaken. De wachtwoorden zijn alleen bekend bij aangewezen medewerkers en kunnen alleen worden gebruikt binnen een tijdsperiode die is geconfigureerd in azure AD PIM.

  Contoso-beveiligingsbeheerders hebben minder beheerdersrollen toegewezen aan accounts die geschikt zijn voor de functie van de IT-werknemer.

  Zie [Informatie over beheerdersrollen in Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) voor meer informatie.

- MFA voor alle gebruikersaccounts

  MFA voegt een extra beschermingsniveau voor het aanmeldingsproces toe. Gebruikers moeten een telefoongesprek, een SMS-bericht of een app-melding op hun smartphone erkennen na de juiste invoer van het wachtwoord. Met MFA zijn Azure AD-gebruikersaccounts beveiligd tegen niet-geautoriseerde aanmelding, ook als het wachtwoord van een account is aangetast.

   - Voor het beschermen tegen compromissen van het Microsoft 365-abonnement heeft Contoso MFA nodig voor alle algemene beheerdersaccounts.
   - Ter bescherming tegen phishingaanvallen, waar een kwaadwillende gebruiker de referenties van een vertrouwde persoon binnen de organisatie misbruikt en schadelijke e-mails verzendt, heeft Contoso MFA ingeschakeld voor alle gebruikersaccounts, inclusief managers en leidinggevenden.

- Veiligere apparaat- en toepassingstoegang met beleid voor voorwaardelijke toegang

  Contoso gebruikt [beleid voor voorwaardelijke toegang](../security/office-365-security/microsoft-365-policies-configurations.md) voor identiteiten, apparaten, Exchange Online en SharePoint. Het beleid voor voorwaardelijke toegang voor identiteiten houdt onder meer in dat gebruikers met een hoog risico hun wachtwoord moeten wijzigen. Daarnaast kunnen klanten geen gebruikmaken van apps die moderne verificatie niet ondersteunen. Apparaatbeleid omvat onder meer de definitie van goedgekeurde apps en het eisen van conforme pc's en mobiele apparaten. Exchange Online-beleid voor voorwaardelijke toegang omvat onder meer het blokkeren van ActiveSync-clients en de installatie van Office 365-berichtversleuteling. SharePoint-beleid voor voorwaardelijke toegang omvat onder meer extra beveiliging voor gevoelige en sterk gereglementeerde sites.

- Windows Hello voor Bedrijven

  Contoso heeft [Windows hello voor bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) gebruikt om uiteindelijk niet langer wachtwoorden toe te staan via sterke tweeledige verificatie op pc's en mobiele apparaten met Windows 10 Enterprise.

- Windows Defender Credential Guard

  Voor het blokkeren van doel aanvallen en malware die in het besturingssysteem worden uitgevoerd met beheerdersbevoegdheden, Contoso heeft [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) via Active Directory-groepsbeleid uitgeschakeld.

## <a name="threat-protection"></a>Bedreigingsbeveiliging

- Bescherming tegen malware met Windows Defender Antivirus

  Contoso gebruikt [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) voor bescherming tegen malware en antimalwarebeheer voor pc's en apparaten met Windows 10 Enterprise.

- Een veilige e-mailstroom en controlelogboekregistratie voor postvakken met Office 365 Advanced Threat Protection 

  Contoso gebruikt Exchange Online Protection en [Office 365 ATP (Advanced Threat Protection)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) om zich te beschermen tegen onbekende malware, virussen en schadelijke URL's die worden verstuurd via e-mailberichten.

  Contoso heeft ook gecontroleerd of de auditlogboek registratie voor postvakken van gebruikers aanmeldt, berichten verzendt en andere activiteiten verricht van de eigenaar van het postvak, een gedelegeerde gebruiker of beheerder.

- Controle op en voorkoming van aanvallen met dreigingsonderzoek en -reacties in Office 365

  Contoso gebruikt [Office 365 Threat onderzoek en respons](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) voor het beschermen van gebruikers door eenvoudig te identificeren en te beschermen tegen aanvallen, en om toekomstige aanvallen te voorkomen.

- Bescherming tegen geavanceerde aanvallen met Advanced Threat Analytics

  Contoso gebruikt [ATA (Advanced Threat Analytics)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) om zichzelf te beschermen tegen geavanceerde doelgerichte aanvallen.  ATA analyseert, leert en identificeert automatisch normaal en abnormaal gedrag van entiteiten (gebruikers, apparaten en resources).

## <a name="information-protection"></a>Gegevensbescherming

- Gevoelige en sterk gereglementeerde digitale activa beschermen met Azure Information Protection-labels

  Contoso heeft drie niveaus van gegevensbescherming ingesteld en [Microsoft 365-vertrouwelijkheidslabels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) geïmplementeerd die gebruikers kunnen toepassen op digitale activa. Voor hun handelsgeheimen en andere intellectuele eigendomsrechten contoso gebruikt contoso sublabels voor zeer gereguleerde gegevens. Met dit proces versleutelt u inhoud en beperkt u de toegang tot bepaalde gebruikersaccounts en groepen.

- Gegevensverlies op intranet voorkomen met preventie van gegevensverlies

  Contoso geconfigureerd voor [preventie van gegevensverlies](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) voor Exchange Online, SharePoint en OneDrive voor bedrijven om te voorkomen dat gebruikers per ongeluk of opzettelijk gevoelige gegevens delen.

- Gegevenslekken op apparaten voorkomen met Windows-gegevensbescherming

  Contoso maakt gebruik van [Windows-informatiebescherming (OHW)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) voor het beschermen van gegevens op basis van Internet-apps en-services en-apps en-gegevens op bedrijfseigen apparaten en persoonlijke apparaten die werknemers naar het werk brengen.

- Cloudbewaking met Microsoft Cloud App Security

  Contoso gebruikt [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) om haar cloudomgeving in kaart te brengen, het gebruik te bewaken en beveiligingsgebeurtenissen en -incidenten te detecteren. *Microsoft Cloud App Security is allen beschikbaar bij Microsoft 365 E5.*

- Apparaatbeheer met Microsoft Intune

  Contoso gebruikt [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) om mobiele apparaten en de apps die daarop worden uitgevoerd, te registreren, te beheren en te configureren. Beleid voor voorwaardelijke toegang voor apparaten vereist ook goedgekeurde apps en conforme pc's en mobiele apparaten.

## <a name="security-management"></a>Beveiligingsbeheer

- Centraal beveiligingsdashboard voor IT met Azure Security Center

  Contoso gebruikt het [Azure-Beveiligingscentrum](https://azure.microsoft.com/services/security-center/) voor een uniforme weergave van beveiliging en risico beveiliging, voor het beheren van beveiligingsbeleid voor de werkbelasting en om te reageren op cyberattacks.

- Centraal beveiligingsdashboard voor gebruikers met Windows Defender-beveiligingscentrum

  Contoso heeft de [Windows-beveiligings-app](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) geïmplementeerd op de pc's en apparaten met Windows 10 Enterprise, zodat gebruikers hun beveiliging posture in één oogopslag kunnen zien en actie kunnen ondernemen.
